The primary library for networking in C++ is `asio` from the `boost` library, it can be used as a part of `boost` or standalone.

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



See also:
- [[Asynchronous Programming]]
- [[Networking]]
- [[C++ friend]]
- [Networking in C++ Part #1: MMO Client/Server, ASIO & Framework Basics](https://www.youtube.com/watch?v=2hNdkYInj4g&list=PLIXt8mu2KcUJOwdLMp-Z-cDIZA1aZfVTN&index=1)