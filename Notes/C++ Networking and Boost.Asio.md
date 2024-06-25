The primary library for networking in C++ is `asio` (asynchronous input output) from the `boost` library, it can be used as a part of `boost` or standalone.

Normally you'd have a message type/struct that contains a fixed size header with an ID and size of the subsequent message in bytes, then the message body of size bytes specified in that header.

Example:
```cpp
template <typename T>
struct message_header{
	T id{};
	uint32_t size = 0;
}
template <typename T>
struct message{
	message_header<T> header{};
	std::vector<uint8_t> body;

	size_t size() const{
		return sizeof(message_header<T>) + body.size();
	}

	// Override for the std::cout compat - produces friendly description of msg
	friend std::ostream& operator << (std::ostream &os, const message<T> &msg){
		os << "ID:" << int(msg.header.id) << " Size:" << msg.header.size;
		return os;
	}
}
```

## A practical example using `asio`

```cpp
#include <iostream>

#define ASIO_STANDALONE /* Tells asio to run in standalone mode instead of via the boost library */

#include <asio.hpp>
#include <asio/ts/buffer.hpp>
#include <asio/ts/internet.hpp>

void GrabSomeData(asio::ip::tcp::socket &socket){
	socket.async_read_some(asio::buffer(vBuffer.data(), vBuffer.size()),
	[&](std::error_code ec, std::size_t length){
		if(!ec){
			std::cout << "\n\nRead " << length << " bytes\n\n";
			for(int i = 0; i < length; i++)
				std::cout << vBuffer[i];

			GrabSomeData(socket);
		}
	}
}

int main(){
	asio error_code ec;
	asio::io_context context;

	asio::io_context:;work idleWork(context); // Fake work to prevent immediate exit due to idleness

	std::thread thrContext = std::thread([&]() {context.run();});

	asio::ip::tcp::endpoint endpoint(asio::ip::make_address("93.184.216.34", ec), 80);

	asio::ip::tcp::socket socket(context);

	socket.connect(endpoint, ec);

	if(ec){
		std::cout << "Failed to connect to address.\n" << ec.message << std::endl;
	}

	if(socket.is_open()){
		/* do something */

		socket.write_some(asio::buffer("Hello", sRequest.size()), ec);

		GrabSomeData(socket);
	}

	return 0;
}
```

## I/O services and I/O objects

I/O services abstract [[Operating Systems]] interfaces that process data async, I/O objects initiate async operations.

Boost defines `boost::asio::io_service` as a single class for I/O service objects, several classes for I/O objects exist depending on the task (e.g. `boost::asio::ip::tcp::socket`).

Example: Two asynchronous operations with `boost::asio::steady_timer`
```cpp
#include <boost/asio/io_service.hpp>
#include <boost/asio/steady_timer.hpp>
#include <chrono>
#include <iostream>

using namespace boost::asio;

int main()
{
  io_service ioservice;

  steady_timer timer1{ioservice, std::chrono::seconds{3}};
  timer1.async_wait([](const boost::system::error_code &ec)
    { std::cout << "3 sec\n"; });

  steady_timer timer2{ioservice, std::chrono::seconds{4}};
  timer2.async_wait([](const boost::system::error_code &ec)
    { std::cout << "4 sec\n"; });

  ioservice.run();
}
```

## Downloading a web page with Boost.Asio

A web client with `boost::asio::ip::tcp::socket`

```cpp
#include <boost/asio/io_service.hpp>
#include <boost/asio/write.hpp>
#include <boost/asio/buffer.hpp>
#include <boost/asio/ip/tcp.hpp>
#include <array>
#include <string>
#include <iostream>

using namespace boost::asio;
using namespace boost::asio::ip;

io_service ioservice;
tcp::resolver resolv{ioservice};
tcp::socket tcp_socket{ioservice};
std::array<char, 4096> bytes;

void read_handler(const boost::system::error_code &ec,
  std::size_t bytes_transferred)
{
  if (!ec)
  {
    std::cout.write(bytes.data(), bytes_transferred);
    tcp_socket.async_read_some(buffer(bytes), read_handler);
  }
}

void connect_handler(const boost::system::error_code &ec)
{
  if (!ec)
  {
    std::string r =
      "GET / HTTP/1.1\r\nHost: theboostcpplibraries.com\r\n\r\n";
    write(tcp_socket, buffer(r));
    tcp_socket.async_read_some(buffer(bytes), read_handler);
  }
}

void resolve_handler(const boost::system::error_code &ec,
  tcp::resolver::iterator it)
{
  if (!ec)
    tcp_socket.async_connect(*it, connect_handler);
}

int main()
{
  tcp::resolver::query q{"theboostcpplibraries.com", "80"};
  resolv.async_resolve(q, resolve_handler);
  ioservice.run();
}
```

## [Boost.Asio Coroutines](https://theboostcpplibraries.com/boost.asio-coroutines)

Further: [[Coroutines]]


See also:
- [[Asynchronous Programming]]
- [[Networking]]
- [[C++ friend]]
- [Networking in C++ Part #1: MMO Client/Server, ASIO & Framework Basics](https://www.youtube.com/watch?v=2hNdkYInj4g&list=PLIXt8mu2KcUJOwdLMp-Z-cDIZA1aZfVTN&index=1)
- [The Boost C++ Libraries - Boost.Asio](https://theboostcpplibraries.com/boost.asio)
- [Boost.Asio - Boost.org](https://www.boost.org/doc/libs/1_85_0/doc/html/boost_asio/overview.html)
- [Beej's Guide to Network Programming](https://beej.us/guide/bgnet/)