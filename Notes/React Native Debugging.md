## LogBox

New feature, makes visualising and using logs easier.
- Better error formatting
- Improved warnings
- Provideds a component stack instead of a raw call stack
- Customisable

## Sourcemaps

A type of file that maps the original source code to a mini or transpiled version, aids in debugging because errors can be mapped back to their original source code location.

Types:
- `eval`: Generates sourcemaps, less detailed than other options.
- `cheap-module-source-map`: Simple line-to-line mapping without column info, faster but less accurate than `source-map`.
- `cheap-source-map`: As above but supports modules.
- `source-map`: Full source mapping but slower than the other options.

## DevTools

You could also use the [React Developer Tools](https://github.com/facebook/react/tree/main/packages/react-devtools) to debug the React component hierachy directly.


See also:
- [React Native Debugging Documentation](https://reactnative.dev/docs/debugging)
- [LogBox Documentation](https://reactnative.dev/docs/debugging#logbox)