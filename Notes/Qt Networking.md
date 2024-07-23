>The Qt Network module offers classes that allow you to write TCP/IP clients and servers. It offers lower-level classes such as [QTcpSocket](https://doc.qt.io/qt-6/qtcpsocket.html), [QTcpServer](https://doc.qt.io/qt-6/qtcpserver.html) and [QUdpSocket](https://doc.qt.io/qt-6/qudpsocket.html) that represent low level network concepts, and high level classes such as [QNetworkRequest](https://doc.qt.io/qt-6/qnetworkrequest.html), [QNetworkReply](https://doc.qt.io/qt-6/qnetworkreply.html) and [QNetworkAccessManager](https://doc.qt.io/qt-6/qnetworkaccessmanager.html) to perform network operations using common protocols.

Pseudo-code example:
```cpp
QNetworkAccessManager;
QNetworkReply* get(const QNetworkRequest &request);
QNetworkReply* m_reply;
void finished();
void MyClass::onFinished() /* Feed to */ m_reply
QByteArray result = m_reply->readAll(); /* Outputs all data as a byte array */
```

You can also use a [[JSON]] object instead of a byte array, or any other alternative provided by [[Qt QML (Qt Quick)]] for your purposes.

`QUdpSocket` and `QTcpSocket` enable [[Networking]] via [[Transmission Control Protocol (TCP)]] and [[User Datagram Protocol (UDP)]].


See also:
- [[C++]]
- [Network Programming with Qt](https://doc.qt.io/qt-6/qtnetwork-programming.html)