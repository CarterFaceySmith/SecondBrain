What the fuck is a listing? God damn it, just googled and this is just used as a verb, it means listing things, bro.

*So*, to **list shit** in [[React Native]], we can use the following:

`FlatList`: Scrollable list component that renders large numbers of items efficiently.

```jsx
import { FlatList, Text } from 'react-native';

const data = [
  { id: 1, text: 'Item 1' },
  { id: 2, text: 'Item 2' },
  { id: 3, text: 'Item 3' },
];

const renderItem = ({ item }) => <Text>{item.text}</Text>;

const MyFlatList = () => (
  <FlatList
    data={data}
    renderItem={renderItem}
    keyExtractor={item => item.id.toString()}
  />
);
```

Additionally, `FlatList` supports-Headers, Footers, Pull-to-refresh, and Horizontal scrolling, among other things.

`SectionList`: Similar to above but used when you want to display data in separate sections with section headers, a la tabular data.

```jsx
import { FlatList, Text } from 'react-native';

const data = [
  { id: 1, text: 'Item 1' },
  { id: 2, text: 'Item 2' },
  { id: 3, text: 'Item 3' },
];

const renderItem = ({ item }) => <Text>{item.text}</Text>;

const MyFlatList = () => (
  <FlatList
    data={data}
    renderItem={renderItem}
    keyExtractor={item => item.id.toString()}
  />
);
```

`VirtualizedList`: First off another victim of the American spelling programming plague, but it's a lower level component for rendering large lists with better control over performance.

```jsx
import { VirtualizedList, Text } from 'react-native';

const data = [
  { id: 1, text: 'Item 1' },
  { id: 2, text: 'Item 2' },
  { id: 3, text: 'Item 3' },
];

const getItemCount = data => data.length;
const getItem = (data, index) => data[index];

const renderItem = ({ item }) => <Text>{item.text}</Text>;

const MyVirtualizedList = () => (
  <VirtualizedList
    data={data}
    renderItem={renderItem}
    keyExtractor={item => item.id.toString()}
    getItemCount={getItemCount}
    getItem={getItem}
  />
);
```

## Going Deeper on Listing Shit in React Native

### ScrollView Component

- `ScrollView` is just a generic scrolling container, wrap what you have listed in it and watch it scroll.

```jsx
import { VirtualizedList, Text } from 'react-native';

const data = [
  { id: 1, text: 'Item 1' },
  { id: 2, text: 'Item 2' },
  { id: 3, text: 'Item 3' },
];

const getItemCount = data => data.length;
const getItem = (data, index) => data[index];

const renderItem = ({ item }) => <Text>{item.text}</Text>;

const MyVirtualizedList = () => (
  <VirtualizedList
    data={data}
    renderItem={renderItem}
    keyExtractor={item => item.id.toString()}
    getItemCount={getItemCount}
    getItem={getItem}
  />
);
```

### RefreshControl Component

- `RefreshControl` is a component used to provide that sweet sweet pull-to-refresh functionality for scrollable container components as per above.

```jsx
import React, { useState } from 'react';
import { FlatList, RefreshControl, Text } from 'react-native';

const App = () => {
    const [refreshing, setRefreshing] = useState(false);

    const fetchData = () => {
        // Fetch the data and update your state accordingly
    };

    const onRefresh = () => {
        setRefreshing(true);
        fetchData().then(() => {
            setRefreshing(false);
        });
    };

    return (
        <FlatList
            data={['Item 1', 'Item 2', 'Item 3']}
            renderItem={({ item }) => <Text>{item}</Text>}
            refreshControl={
                <RefreshControl refreshing={refreshing} onRefresh={onRefresh} />
            }
        />
    );
};

export default App;
```

## Optimising FlatList

### 1. Set `windowSize`

`windowSize` is a prop that determines the number of pages rendered above and below the current window. By default, this value is 21. You can decrease it based on your needs to reduce the number of off-screen rendered components.

Example:

```jsx
<FlatList
  data={data}
  renderItem={renderItem}
  keyExtractor={item => item.id}
  windowSize={10}
/>
```

### 2. Set `removeClippedSubviews`

Enable the `removeClippedSubviews` prop to unmount components that are off the screen.

Example:

```jsx
<FlatList
  data={data}
  renderItem={renderItem}
  keyExtractor={item => item.id}
  removeClippedSubviews={true}
/>
```

### 3. Set `maxToRenderPerBatch`

`maxToRenderPerBatch` prop helps to control the number of items to be rendered per batch. By default, this is set to 10. Optimise this value according to your list’s requirements.

Example:

```jsx
<FlatList
  data={data}
  renderItem={renderItem}
  keyExtractor={item => item.id}
  maxToRenderPerBatch={5}
/>
```

### 4. Set `initialNumToRender`

`initialNumToRender` is used to set the number of items to be rendered initially. Setting this value to a reasonable number can help in avoiding blank screens on load.

Example:

```jsx
<FlatList
  data={data}
  renderItem={renderItem}
  keyExtractor={item => item.id}
  initialNumToRender={10}
/>
```

### 5. Set `getItemLayout`

Using the `getItemLayout` prop allows you to specify the exact dimensions of each item. This prevents the need for measuring them dynamically, resulting in improved performance.

Example:

```jsx
<FlatList
  data={data}
  renderItem={renderItem}
  keyExtractor={item => item.id}
  getItemLayout={(data, index) => (
    {length: ITEM_HEIGHT, offset: ITEM_HEIGHT * index, index}
  )}
/>
```