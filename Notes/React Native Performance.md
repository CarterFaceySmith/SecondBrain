## Common Problem Sources

### 1. Console Logs

Excessive console logs can lead to decreased performance in React Native, especially in debug mode. In order to avoid this, keep the usage of console logging to a minimum, and clean up unnecessary logs before releasing the app.

### 2. Images

Heavy and unoptimised images can lead to performance issues in React Native. To avoid this, use the following techniques:

- Optimise image size and resolution before bundling them in the application.
- Use `resizeMode` prop on the `Image` component to cache images for better rendering.

```jsx
<Image source={require('./my-image.png')} resizeMode="cover" />
```

### 3. Inline Functions and Styles

Using inline functions and styles within components can lead to unnecessary re-rendering and performance issues. Instead, define functions and styles outside of the component render method.

```jsx
// Bad
render() {
  return (
    <TouchableOpacity onPress={() => this.onPress()}>
      <Text style={{fontSize: 16, color: 'blue'}}>Click me</Text>
    </TouchableOpacity>
  );
}

// Good
const styles = StyleSheet.create({
  buttonText: {
    fontSize: 16,
    color: 'blue',
  },
});

onPressHandler = () => {
  // Handle press
};

render() {
  return (
    <TouchableOpacity onPress={this.onPressHandler}>
      <Text style={styles.buttonText}>Click me</Text>
    </TouchableOpacity>
  );
}
```

### 4. PureComponent and React.memo

Components that extend `React.PureComponent` or are wrapped in `React.memo()` can lead to performance issues in case they’re updating frequently and causing unnecessary re-renders. Make sure to only use them when appropriate to avoid performance bottlenecks.

### 5. ListView and FlatList

When working with large lists in React Native, using `ListView` instead of `FlatList` can cause performance issues. Replace `ListView` with the more performant `FlatList` or `SectionList` components.

```jsx
// Use FlatList instead of ListView
<FlatList
  data={this.state.data}
  renderItem={({item}) => <MyListItemComponent item={item} />}
  keyExtractor={(item) => item.id}
/>
```

### 6. JavaScript Thread Blockage

Blocking the JavaScript [[Threads]] with expensive synchronous computations can lead to poor performance. Make sure to handle heavy computations asynchronously or offload them to native modules.

## RAM Bundles + Inline Requires

If you have a large app you may want to consider the [[RAM]] bundle format, and using inline requires. This is useful for apps that have a large number of screens which may not ever be opened during a typical usage of the app. 

Generally it is useful to apps that have large amounts of code that are not needed for a while after startup. For instance the app includes complicated profile screens or lesser used features, but most sessions only involve visiting the main screen of the app for updates. 

We can optimise the loading of the bundle by using the RAM format and requiring those features and screens inline (when they are actually used).

## [Speeding Up Your Builds](https://reactnative.dev/docs/build-speed)


See also:
- [[React Native Core Components]]
- [React Native Profiling](https://reactnative.dev/docs/profiling)