AKA how does the user interact with your app?

## Touchables

- **`TouchableHighlight`**: Responds to the press event with a visual effect, such as highlighting the touched area.

```js
    import { TouchableHighlight, Text } from 'react-native';
    
    function MyButton() {
      return (
        <TouchableHighlight onPress={() => console.log('Button pressed')}>
          <Text>Press me!</Text>
        </TouchableHighlight>
      );
    }
```

- **`TouchableOpacity`**: Responds to the press events by making the touched area semi-transparent.

```js
    import { TouchableOpacity, Text } from 'react-native';
    
    function MyButton() {
      return (
        <TouchableOpacity onPress={() => console.log('Button pressed')}>
          <Text>Press me!</Text>
        </TouchableOpacity>
      );
    }
```

- **`TouchableWithoutFeedback`**: Responds to the press events without any visual feedback.

```js
    import { TouchableWithoutFeedback, Text } from 'react-native';
    
    function MyButton() {
      return (
        <TouchableWithoutFeedback onPress={() => console.log('Button pressed')}>
          <Text>Press me!</Text>
        </TouchableWithoutFeedback>
      );
    }
```

- **`TouchableNativeFeedback`**: Provides additional Android-specific visual feedback.

```js
    import { TouchableNativeFeedback } from 'react-native';
    
    <TouchableNativeFeedback
      onPress={() => {
        alert('Tapped!');
      }}
    >
      <Text>Tap me</Text>
    </TouchableNativeFeedback>
```

- **`TouchableScale`**: The view will slightly change scale when pressed.
   
```js
    import { TouchableScale } from 'react-native-touchable-scale';
    
    <TouchableScale
      onPress={() => {
        alert('Tapped!');
      }}
      activeScale={0.9}
    >
      <Text>Tap me</Text>
    </TouchableScale>
```

## Gesture Responder System

The Gesture Responder System is a low-level API for capturing touch events and managing touch responsiveness in a React Native application. It allows components to take ownership of touch events and determine how they should be handled.

```js
import { View, Text, StyleSheet } from 'react-native';

function MyComponent() {
  return (
    <View
      style={styles.container}
      onStartShouldSetResponder={() => true}
      onResponderGrant={(event) => console.log('Touch started')}
      onResponderMove={(event) => console.log('Touch moving')}
      onResponderRelease={(event) => console.log('Touch released')}
    >
      <Text>Touch me!</Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    borderWidth: 1,
    borderColor: 'black',
    padding: 10,
  },
});
```

## PanResponder

PanResponder is a gesture responder helper that deals with touch events using the Gesture Responder System. It simplifies creating components that respond to various touch events.

```js
import { PanResponder, View, Text, StyleSheet } from 'react-native';

function MyComponent() {
  const panResponder = PanResponder.create({
    onStartShouldSetPanResponder: () => true,
    onPanResponderGrant: (event) => console.log('Touch started'),
    onPanResponderMove: (event) => console.log('Touch moving'),
    onPanResponderRelease: (event) => console.log('Touch released'),
  });

  return (
    <View style={styles.container} {...panResponder.panHandlers}>
      <Text>Touch me!</Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    borderWidth: 1,
    borderColor: 'black',
    padding: 10,
  },
});
```

## Animated

The `Animated` library provides a way to create smooth animations in a React Native application. It can handle various types of animations, such as opacity, scaling, and rotation.

```js
import { Animated, TouchableOpacity } from 'react-native';

function MyAnimatedComponent() {
  const opacity = new Animated.Value(1);

  function animateOpacity() {
    Animated.timing(opacity, {
      toValue: 0,
      duration: 1000,
      useNativeDriver: true,
    }).start();restartnow
    
  }

  return (
    <TouchableOpacity onPress={animateOpacity}>
      <Animated.View style={{ opacity }}>
        {/* Your content */}
      </Animated.View>
    </TouchableOpacity>
  );
}
```

Further: [[React Native Animations]]

## Scrolling

See the ScrollView and FlatList portions of [[React Native Core Components]].

## Swiping

To implement swiping in React Native, the community-driven package `react-native-gesture-handler` is commonly used. One of its components is `Swipeable`, which allows you to create swipeable elements with custom swipe actions.

Example:

```jsx
import React from 'react';
import { Text, View } from 'react-native';
import { RectButton } from 'react-native-gesture-handler';
import Swipeable from 'react-native-gesture-handler/Swipeable';

const RightActions = (progress, dragX, onPress) => {
  return (
    <RectButton onPress={onPress}>
      <View>
        <Text>Delete</Text>
      </View>
    </RectButton>
  );
};

const SwipeableExample = () => {
  const handleDelete = () => {
    alert('Delete action');
  };

  return (
    <Swipeable
      renderRightActions={(progress, dragX) =>
        RightActions(progress, dragX, handleDelete)
      }
    >
      <View>
        <Text>Swipeable Element</Text>
      </View>
    </Swipeable>
  );
};
```