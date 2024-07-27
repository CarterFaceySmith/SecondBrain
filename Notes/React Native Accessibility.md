Create apps that are usable by everyone bro, c'mon now.

[[React Native]] gives us a few props that can be applied to components for enhancing this.

`accessible` : (Boolean) - Indicates if the element can be focused by screen readers.

```js
<TouchableOpacity accessible={true} />
```

`accessibilityLabel` : (String) - Used by the screen reader to describe the element to the user.

```js
<TouchableOpacity accessibilityLabel="Tap me!">
```

`accessibilityHint` : (String) - Gives a hint to the user of the components behaviour.

```js
<TouchableOpacity accessibilityHint="Tapping this button will show a welcome text">
```

`accessibilityRole` : (String) - Describes the role of the element for the screen reader.

```js
<TextInput accessibilityRole="search" />
```

`accessibilityValue` : (Object with properties: min, max, now) - Defines the accessibility values for elements such as progress bars or sliders, among others.

```js
<Slider
  accessibilityValue={{
    min: 0,
    max: 100,
    now: 50,
  }}
/>
```

`accessibilityState` : (Object) - Represents the current state of the component.

```js
<TouchableOpacity
  accessibilityState={{
    disabled: false,
    selected: true,
  }}
/>
```

`accessibilityActions` and `onAccessibilityAction` are used to create custom actions.

```js
import { AccessibilityInfo, Text, View } from 'react-native';

function CustomButton() {
  const [count, setCount] = React.useState(0);

  const onIncrement = () => {
    setCount(count + 1);
  };

  React.useEffect(() => {
    const announce = () => {
      AccessibilityInfo.announceForAccessibility(`Count raised to ${count}`);
    };
    announce();
  }, [count]);

  return (
    <View
      accessible={true}
      accessibilityActions={[
        { name: "increment", label: "increase count" },
      ]}
      onAccessibilityAction={(event) => {
        switch (event.nativeEvent.actionName) {
          case "increment":
            onIncrement();
            break;
        }
      }}
    >
      <Text>Increment Counter: {count}</Text>
    </View>
  );
}
```