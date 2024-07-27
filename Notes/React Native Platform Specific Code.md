
Despite being platform agnostic, [[React Native]] does support having parts of your app maintained differently depending on the target [[Operating Systems]].

How?

## Option 1: Platform Module

Detects which platform the app is running on and allows that to be used in rendering.

```jsx
import { Platform, StyleSheet, Text } from 'react-native';

const ComponentWithPlatformSpecificCode = () => {
  return <Text style={styles.content}>Hello World!</Text>;
};

const styles = StyleSheet.create({
  content: {
    color: Platform.select({
      ios: 'blue',
      android: 'green',
    }),
  },
});

export default ComponentWithPlatformSpecificCode;
```

## Option 2: File Extensions

You can prepend `.ios` or `.android` before the `.js` of some files to have [[React Native]] automatically pick up the right file depending on the platform it is on.

**Example:**

Let’s say you have two files in your project, `Header.ios.js` and `Header.android.js`. When you import the `Header` component in your code, React Native will automatically import the correct file for the platform.

```jsx
// App.js
import Header from './Header';
```



Further:
- [[React Native Web]]