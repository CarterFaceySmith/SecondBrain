Frame rates represent the number of frames (or images) displayed per second in an animation or video. 

In general, frame rates can be categorised into two types:

- **Static Frame Rate**: This is when your application’s frame rate remains constant during its runtime.

- **Adaptive Frame Rate**: This is when your application adjusts the frame rate according to device performance and available resources.

### Animated library

This library provides a set of methods and components that help you manage animations efficiently. By using the `Animated` library, you can define animations declaratively, avoid unnecessary render cycles, and utilise the native driver to offload animation from the [[JavaScript]] thread.

Here’s an example of using the `Animated` library to create a simple fade-in animation:

```jsx
import React, { useEffect, useRef } from 'react';
import { Animated, StyleSheet, View } from 'react-native';

const FadeIn = (props) => {
  const opacity = useRef(new Animated.Value(0)).current;

  useEffect(() => {
    Animated.timing(opacity, {
      toValue: 1,
      duration: 500,
      useNativeDriver: true, // This line offloads animation to the native driver
    }).start();
  }, []);

  return (
    <Animated.View
      style={[
        styles.container,
        {
          opacity: opacity, // This line applies the animated opacity value
        },
      ]}
    >
      {props.children}
    </Animated.View>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
  },
});

export default FadeIn;
```