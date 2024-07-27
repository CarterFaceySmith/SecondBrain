Deep linking is a technique used in mobile applications that allows you to open a specific screen, content, or functionality within the application using a URL or a custom URL scheme. 

Deep linking can be triggered by clicking on a link in an email, scanning a QR code, or through a push notification.

There are two types of deep links:

1. **Universal Links** (iOS) / **App Links** (Android): These are [[HTTPS]] URLs that allow the user to navigate to a specific screen when the app is installed and fallback to a specified website when the app is not installed.
2. **Custom URL Schemes**: Unique URLs, like `myapp://my-screen`, that can open the app directly to a specific screen when clicked.

## Handling Deep Links in React Native

In [[React Native]], you can handle deep links using the `Linking` module which provides the necessary methods to work with deep links.

```jsx
import { Linking } from 'react-native';
```

Add a listener that will be triggered when the app receives a deep link.

You can add the listener in the `componentDidMount` lifecycle method and remove it in the `componentWillUnmount` method.

```jsx
import React from 'react';
import { Linking, Text, View } from 'react-native';

class App extends React.Component {
  componentDidMount() {
    Linking.addEventListener('url', this.handleOpenURL);
  }

  componentWillUnmount() {
    Linking.removeEventListener('url', this.handleOpenURL);
  }

  handleOpenURL(event) {
    // Handle your deep link logic
    console.log('Received deep link: ', event.url);
  }

  render() {
    return (
      <View>
        <Text>Hello from React Native!</Text>
      </View>
    );
  }
}

export default App;
```