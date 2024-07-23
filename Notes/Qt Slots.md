In a [[Qt QML (Qt Quick)]] context, slots are [[Functions]] called in response to certain [[Qt Signals]].

>"A slot is called when a signal connected to it is emitted. Slots are normal [[C++]] functions and can be called normally; their only special feature is that signals can be connected to them.
>
>Since slots are normal member functions, they follow the normal C++ rules when called directly. However, as slots, they can be invoked by any component, regardless of its access level, via a signal-slot connection. This means that a signal emitted from an instance of an arbitrary class can cause a private slot to be invoked in an instance of an unrelated class."