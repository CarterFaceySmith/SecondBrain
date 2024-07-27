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