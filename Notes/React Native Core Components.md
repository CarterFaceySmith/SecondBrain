The keys, the building blocks of [[React Native]] [[User Interface (UI)]] development.

## View Component

- `View` is a fundamental component for constructing the user interface. It is equivalent to a `div` in [[HTML]] and can be used as a [[Containers]] for other components.

```jsx
import React from 'react';
import { StyleSheet, View, Text } from 'react-native';

function App() {
  return (
    <View style={styles.container}>
      <Text>Hello, World!</Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#fff',
    alignItems: 'center',
    justifyContent: 'center',
  },
});

export default App;
```

### SafeAreaView

A variant that helps to adjust UI elements and layout to accommodate stupid shit like notches, etc.

```jsx
import React from 'react';
import { SafeAreaView, StyleSheet, Text } from 'react-native';

const App = () => {
  return (
    <SafeAreaView style={styles.container}>
      <Text>Hello World!</Text>
    </SafeAreaView>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
  },
});

export default App;
```

>Keep in mind that `SafeAreaView` only works on [[iOS]] devices, and has no effect on [[Android]] devices. To handle such cases, you can use platform-specific styles or libraries like `react-native-safe-area-context` which provide more control and customisation options for additional platforms.

### KeyboardAvoidingView

Same shit but for keyboards, let's say you want them to complete a form but they need to have the keyboard and a view of the field at the same time to do that right? Use this.

```jsx
import React from 'react';
import { View, TextInput, StyleSheet, KeyboardAvoidingView } from 'react-native';

const App = () => {
  return (
    <KeyboardAvoidingView
      style={styles.container}
      behavior="padding" // Additional padding when the keyboard is open.
    >
      <TextInput
        placeholder="Type something here"
        style={styles.textInput}
      />
    </KeyboardAvoidingView>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
  },
  textInput: {
    borderWidth: 1,
    borderColor: 'black',
    padding: 10,
    margin: 20,
  },
});

export default App;
```

## Text Component

- `Text` is used to display text content in your app. It is similar to the `p` or `span` elements in HTML.

```jsx
import React from 'react';
import { Text, StyleSheet } from 'react-native';

const SimpleText = () => {
  return (
    <Text style={styles.text} numberOfLines={2} onPress={() => alert('Hello')}>
      This is an example of a Text component in React Native. Tap on me!
    </Text>
  );
};

const styles = StyleSheet.create({
  text: {
    fontSize: 16,
    color: 'blue',
    textAlign: 'center',
    margin: 10,
    fontFamily: 'Arial',
  },
});

export default SimpleText;
```

## Image Component

- `Image` is used to display images in your application. It can load images from local sources or remote URLs. Style needs to be supplied for remote images.

```jsx
import { Image } from 'react-native';

<Image source={require('./assets/logo.png')} />
<Image source={{ uri: 'https://example.com/image.png' }} style={{ width: 200, height: 200 }} />
```

You can set image scaling and positioning with the `resizeMode` prop. It accepts the following values: `cover`, `contain`, `stretch`, `repeat`, and `center`. Default value is `cover`.

## ImageBackground Component

- `ImageBackground` lets you display an image as a background whilst placing further content inside the component. 

```jsx
import React from 'react';
import { View, Text, ImageBackground, StyleSheet } from 'react-native';

const App = () => (
  <ImageBackground
    source={{ uri: 'https://some-image-url.com/background.jpg' }}
    style={styles.background}
    resizeMode="cover"
  >
    <Text style={styles.text}>Hello, World!</Text>
  </ImageBackground>
);

const styles = StyleSheet.create({
  background: {
    flex: 1,
    justifyContent: 'center',
  },
  text: {
    color: 'white',
    fontSize: 42,
    lineHeight: 84,
    fontWeight: 'bold',
    textAlign: 'center',
  },
});

export default App;
```

## TextInput Component

- `TextInput` is a basic input field that allows users to type text into your app. It is similar to the `input` element in [[HTML]].

```jsx
import React, { useState } from 'react';
import { TextInput, View, Button } from 'react-native';

const App = () => {
  const [text, setText] = useState('');

  const handleSubmit = () => {
    alert('You entered: ' + text);
  };

  return (
    <View>
      <TextInput
        style={{ height: 40, borderColor: 'gray', borderWidth: 1 }}
        onChangeText={text => setText(text)}
        value={text}
        placeholder="Enter text here"
      />
      <Button
        onPress={handleSubmit}
        title="Submit"
      />
    </View>
  );
};
```

## Button Component

- `Button` creates clickable buttons, go figure. Triggers an `onPress` event when pressed.

```jsx
import React from 'react';
import { Button } from 'react-native';

const MyButton = () => {
  const onPressHandler = () => {
    alert('Button Pressed');
  };

  return (
    <Button
      title="Click me"
      color="#841584"
      onPress={onPressHandler}
    />
  );
};

export default MyButton;
```

## Switch Component

- `Switch` is used as a toggle or on-off input, simple. Has a boolean value prop and an `onValueChange` event handler which is triggered on toggle.

```jsx
import React, {useState} from 'react';
import {View, Switch, Text} from 'react-native';

const App = () => {
  const [isEnabled, setIsEnabled] = useState(false);

  const toggleSwitch = () => setIsEnabled(previousState => !previousState);

  return (
    <View>
      <Text>Enable Feature:</Text>
      <Switch
     trackColor={{ false: "#767577", true: "#81b0ff" }}
     thumbColor={isEnabled ? "#f5dd4b" : "#f4f3f4"}
      onValueChange={toggleSwitch}
      value={isEnabled}
      />
    </View>
  );
};

export default App;
```

## StatusBar Component

- `StatusBar` controls the appearance of the status bar at the top of the screen, doesn't render visible content, sets native properties that customise the look of platform specific status bars.

```jsx
import React from 'react';
import { View, StatusBar } from 'react-native';

const App = () => {
  return (
    <View>
      <StatusBar barStyle="dark-content" backgroundColor="#F0F0F0" />
      {/* Your other components */}
    </View>
  );
};

export default App;
```

```jsx
<StatusBar
  barStyle="light-content"
  backgroundColor="#6A0E37"
  hidden={false}
  animated={true}
  translucent={true}
/>
```

## TouchableOpacity Component

- `TouchableOpacity` is a wrapper for making elements like `View` and `Text` respond properly to touch events. It provides feedback by reducing the opacity of the wrapped component when pressed.

```jsx
<TouchableOpacity onPress={this.onButtonPress}>
  <Text style={styles.buttonText}>Press me!</Text>
</TouchableOpacity>
```

- `ScrollView` are scrollable [[Containers]] that allows users to scroll through its content. It is useful when you have content that exceeds the available screen size.

```jsx
<ScrollView style={styles.scrollContainer}>
  <Text>Content 1</Text>
  <Text>Content 2</Text>
  {/* ... */}
</ScrollView>
```

- `FlatList` is used to render a list of items using a performant approach. It only renders items that are currently visible on the screen and removes others to save memory.

```jsx
<FlatList
  data={this.state.data}
  renderItem={({ item }) => <Text>{item.name}</Text>}
  keyExtractor={item => item.id}
/>
```

## ActivityIndicator Component

- `ActivityIndicator` shows a spinning animation to indicate activity, technically called a throbber.

```jsx
import React from 'react';
import { ActivityIndicator, View, Text } from 'react-native';

const LoadingScreen = () => (
  <View style={{ flex: 1, justifyContent: 'center', alignItems: 'center' }}>
    <Text>Loading, please wait...</Text>
    <ActivityIndicator size="large" color="#0000ff" />
  </View>
);

export default LoadingScreen;
```

## Modal Component

- `Modal` displays content on top of the current view, creating an overlay.

```jsx
import React, {useState} from 'react';
import {Modal, Text, TouchableHighlight, View, Alert} from 'react-native';

const App = () => {
  const [modalVisible, setModalVisible] = useState(false);

  return (
    <View>
      <Modal
        animationType="slide"
        transparent={true}
        visible={modalVisible}
        onRequestClose={() => {
          Alert.alert('Modal has been closed.');
          setModalVisible(!modalVisible);
        }}>
        <View>
          <View>
            <Text>Hello, I am a Modal!</Text>

            <TouchableHighlight
              onPress={() => {
                setModalVisible(!modalVisible);
              }}>
              <Text>Hide Modal</Text>
            </TouchableHighlight>
          </View>
        </View>
      </Modal>

      <TouchableHighlight
        onPress={() => {
          setModalVisible(true);
        }}>
        <Text>Show Modal</Text>
      </TouchableHighlight>
    </View>
  );
};

export default App;
```

## Pressable Component

- `Pressable` makes any view respond to touch or press events, provides a range of event handlers for managing user interactions, just wrap the component you want to make pressable in the `Pressable` component.

```jsx
import React from 'react';
import { Pressable, Text, StyleSheet } from 'react-native';

export default function CustomButton() {
  return (
    <Pressable
      onPress={() => console.log('Pressed!')}
      style={({ pressed }) => [
        styles.button,
        pressed ? styles.pressedButton : styles.normalButton,
      ]}
    >
      <Text style={styles.buttonText}>Press me</Text>
    </Pressable>
  );
}

const styles = StyleSheet.create({
  button: {
    padding: 10,
    borderRadius: 5,
  },
  normalButton: {
    backgroundColor: 'blue',
  },
  pressedButton: {
    backgroundColor: 'darkblue',
  },
  buttonText: {
    color: 'white',
    textAlign: 'center',
  },
});
```