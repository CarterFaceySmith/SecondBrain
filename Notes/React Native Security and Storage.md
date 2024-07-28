Just some general best practices for [[Application Security]], tailored to [[React Native]].

## 1. Secure Storage

Store sensitive data, such as authentication tokens, encryption keys, or user credentials, securely using a storage solution that comes with built-in [[Encryption]] mechanisms.

For React Native, [react-native-keychain](https://github.com/oblador/react-native-keychain) and [react-native-encrypted-storage](https://github.com/emeraldsanto/react-native-encrypted-storage) are popular libraries handling secure storage.

```jsx
import * as Keychain from 'react-native-keychain';

// Save data to the keychain
await Keychain.setGenericPassword(username, password);

// Retrieve data from the keychain
const credentials = await Keychain.getGenericPassword();
```

Further options:
- [Async Storage](https://github.com/react-native-async-storage/async-storage)
- Expo Secure Store
- Expo File System
- Expo SQLite - Part of the `expo-sqlite` package

AsyncStorage and SecureStorage are more suited for small-scale data storage, while Realm and SQLite support more complex storage and querying needs.

### `expo-secure-store`

- Provided by the `expo` SDK
- Key-value storage system, but not designed for large amounts of data
- Good for keys, tokens, small preferences etc.

1. `expo install expo-secure-store`
2. `import * as SecureStore from 'expo-secure-store';

To save data to the secure store, use the `setItemAsync` method. It takes two arguments: a key and a value. Both should be strings.

```jsx
async function saveData() {
  try {
    await SecureStore.setItemAsync('your_key', 'your_value');
    console.log('Data saved successfully!');
  } catch (error) {
    console.error('Error saving data:', error);
  }
}
```

To retrieve data from the secure store, use the `getItemAsync` method, which takes the key as a parameter and returns a Promise that resolves to the value.

```jsx
async function getData() {
  try {
    const value = await SecureStore.getItemAsync('your_key');
    if (value !== null) {
      console.log('Data retrieved:', value);
    } else {
      console.log('No data found with that key.');
    }
  } catch (error) {
    console.error('Error retrieving data:', error);
  }
}
```

To delete data from the secure store, use the `deleteItemAsync` method. It takes the key as a parameter.

```jsx
async function deleteData() {
  try {
    await SecureStore.deleteItemAsync('your_key');
    console.log('Data deleted successfully!');
  } catch (error) {
    console.error('Error deleting data:', error);
  }
}
```

### `expo-file-system`

1. `expo install expo-file-system`
2. `import * as FileSystem from 'expo-file-system';`

#### Reading a File

```jsx
async function readFileAsync() {
    const fileUri = FileSystem.documentDirectory + 'myFile.txt';

    try {
        const content = await FileSystem.readAsStringAsync(fileUri);
        console.log('File content:', content);
    } catch (error) {
        console.error('Error while reading file:', error);
    }
}
```

#### Writing a File

```jsx
async function writeFileAsync() {
    const fileUri = FileSystem.documentDirectory + 'myFile.txt';
    const content = 'Hello, World!';

    try {
        await FileSystem.writeAsStringAsync(fileUri, content);
        console.log('File written successfully');
    } catch (error) {
        console.error('Error while writing file:', error);
    }
}
```

#### Copying & Moving a File

```jsx
async function copyAndMoveFileAsync() {
    const srcUri = FileSystem.documentDirectory + 'myFile.txt';
    const destUri = FileSystem.documentDirectory + 'copiedFile.txt';

    try {
        await FileSystem.copyAsync({ from: srcUri, to: destUri });
        console.log('File copied successfully');

        const newDestUri = FileSystem.documentDirectory + 'movedFile.txt';
        await FileSystem.moveAsync({ from: destUri, to: newDestUri });
        console.log('File moved successfully');
    } catch (error) {
        console.error('Error while copying/moving file:', error);
    }
}
```

#### Deleting a File

```jsx
async function deleteFileAsync() {
    const fileUri = FileSystem.documentDirectory + 'myFile.txt';

    try {
        await FileSystem.deleteAsync(fileUri);
        console.log('File deleted successfully');
    } catch (error) {
        console.error('Error while deleting file:', error);
    }
}
```

## 2. Secure Communication

Use [[HTTPS]] for network communication with APIs and remote services. This ensures that the data exchanged between server and client is encrypted and secure.

Use the [fetch](https://reactnative.dev/docs/network) method with URLs starting with ‘https://‘.

```jsx
const response = await fetch('https://example.com/api/data');
const data = await response.json();
```

## 3. Minimise Permissions

Request only the necessary permissions from the user that your application needs to function, and do this at runtime when the feature actually needs the permission.

Using [react-native-permissions](https://github.com/zoontek/react-native-permissions), you can request permissions when they are needed:

```jsx
import {check, PERMISSIONS, request, RESULTS} from 'react-native-permissions';

async function requestLocationPermission() {
  const result = await check(PERMISSIONS.IOS.LOCATION_WHEN_IN_USE);

  if (result === RESULTS.DENIED) {
    return await request(PERMISSIONS.IOS.LOCATION_WHEN_IN_USE);
  }

  return result;
}
```

## 4. Validate User Input

Ensure you validate and sanitise all user input before processing it. This helps to prevent potential threats like SQL injection or cross-site scripting (XSS).

Use a validation library like [Yup](https://github.com/jquense/yup) to validate user input.

```jsx
import * as Yup from 'yup';

const loginSchema = Yup.object({
  email: Yup.string().email('Invalid email address').required('Required'),
  password: Yup.string()
    .min(8, 'Password must be at least 8 characters')
    .required('Required'),
});

loginSchema.validate({email: 'user@example.com', password: 'password'});
```

## 5. Keep Dependencies Up to Date

Regularly update your dependencies to ensure they don’t contain known security vulnerabilities. Use tools like [npm audit](https://docs.npmjs.com/cli/commands/npm-audit) and [dependabot](https://github.com/dependabot/dependabot-core) to automatically audit and update your dependencies.

Using npm, you can update your dependencies and check for potential vulnerabilities:

```jsx
npm update
npm audit
```