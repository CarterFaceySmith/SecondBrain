Sometimes a [[React Native]] app needs to access a native platform API that is not available by default in [[JavaScript]], for example the native APIs to access Apple or Google Pay. Maybe you want to reuse some existing [[Objective-C]], [[Swift]], [[Java]] or [[C++]] libraries without having to re-implement it in JavaScript, or write some high performance, multi-threaded code for things like image processing.

The NativeModule system exposes instances of Java/Objective-C/C++ (native) classes to JavaScript (JS) as JS objects, thereby allowing you to execute arbitrary native code from within JS.

There are different ways to write a native module for your React Native application:

1. Creating a local library that can be imported in your React Native application. Read [Creating local libraries](https://reactnative.dev/docs/local-library-setup) guide to learn more.
2. Directly within your React Native application's iOS/Android projects
3. As a NPM package that can be installed as a dependency by your/other React Native applications.


See also:
- [Native Modules Introduction](https://reactnative.dev/docs/native-modules-intro)