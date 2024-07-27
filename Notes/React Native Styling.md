Done via [[JavaScript]] using a subset of [[CSS]] properties. [[React Native]] has its own set of components and styling rules, `StyleSheet`, `View`, and `Text`.

## StyleSheet

`StyleSheet` is a module provided by React Native to manage and optimise styles. It is similar to a CSS stylesheet and helps in creating and working with multiple styles efficiently.

```jsx
import { StyleSheet, View, Text } from 'react-native';

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#fff',
    alignItems: 'center',
    justifyContent: 'center',
  },
  text: {
    fontSize: 20,
    fontWeight: 'bold',
  },
});
```

### Combining styles

You can combine multiple styles by passing an array of styles to the `style` prop of a component. The last style in the array takes precedence if there are conflicting styles.

```jsx
<View style={[styles.container, styles.backgroundRed]}>
  <Text style={styles.text}>Hello, React Native!</Text>
</View>

// Adding backgroundRed to the existing styles
const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#F5FCFF',
  },
  text: {
    fontSize: 20,
    textAlign: 'center',
    margin: 10,
  },
  backgroundRed: {
    backgroundColor: 'red',
  },
});
```

## View and Text components

```jsx
import React from 'react';
import { StyleSheet, View, Text } from 'react-native';

export default function App() {
  return (
    <View style={styles.container}>
      <Text style={styles.text}>Hello, React Native!</Text>
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
  text: {
    fontSize: 20,
    fontWeight: 'bold',
  },
});
```

## Inline styles

```jsx
import React from 'react';
import { View, Text } from 'react-native';

export default function App() {
  return (
    <View
      style={{
        flex: 1,
        backgroundColor: '#fff',
        alignItems: 'center',
        justifyContent: 'center',
      }}
    >
      <Text
        style={{
          fontSize: 20,
          fontWeight: 'bold',
        }}
      >
        Hello, React Native!
      </Text>
    </View>
  );
}
```

## Layouts

Done via the Flexbox styling system, which consists of the `container`, `main axis`, and `cross axis`.

- The `container` is the parent flex container that holds and distributes all the child elements.
- The `main axis` is the primary direction of the layout (horizontal or vertical).
- The `cross axis` is the perpendicular direction, opposite of the main axis.

Here are some of the most commonly used Flexbox styles:

- **`flexDirection`**: This style specifies the primary axis using four possible values: `row`, `row-reverse`, `column`, or `column-reverse`.

```jsx
<View style={{flexDirection: 'row'}}>
  <Text>First child</Text>
  <Text>Second child</Text>
</View>
```

- **`alignItems`**: This style is used to align the child items along the cross-axis. It uses the values `flex-start`, `flex-end`, `center`, `stretch`, or `baseline`.

```jsx
<View style={{flexDirection: 'row', alignItems: 'center'}}>
  <Text>First child</Text>
  <Text>Second child</Text>
</View>
```

- **`justifyContent`**: This style is used to align the child items along the main axis. It accepts the values `flex-start`, `flex-end`, `center`, `space-between`, or `space-around`.

```jsx
<View style={{flexDirection: 'row', justifyContent: 'space-between'}}>
  <Text>First child</Text>
  <Text>Second child</Text>
</View>
```

- **`flexWrap`**: Set to either `wrap` or `nowrap` to specify if child items should wrap around to the next line when there’s not enough space on the current line.

```jsx
<View style={{flexDirection: 'row', flexWrap: 'wrap'}}>
  <Text>First child</Text>
  <Text>Second child</Text>
  <Text>Third child</Text>
</View>
```

- **`flex`**: This style determines how the child items grow or shrink when there’s remaining space in the container. It’s a shorthand for `flex-grow`, `flex-shrink`, and `flex-basis`.

```jsx
<View style={{flexDirection: 'row'}}>
  <Text style={{flex: 1}}>First child</Text>
  <Text style={{flex: 2}}>Second child</Text>
</View>
```


See also:
- [[React Native Core Components]]