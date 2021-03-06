# hippy-react-demo

![Hippy Group](https://img.shields.io/badge/group-Hippy-blue.svg)

## Web project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

> For web target, the demo project has defined a [alias to local hippy-react-web](./scripts/hippy-webpack.web.js#L85), you should remove the section and keeps `@hippy/react-web` is the alias for `@hippy/react`.

### Compiles and minifies for production
```
npm run build
```

> For web target, the demo project has defined a [alias to local hippy-react-web](./scripts/hippy-webpack.web.js#L85), you should remove the section and keeps `@hippy/react-web` is the alias for `@hippy/react`.

## Debug the JS codes in native

### Build and watch for development

```
npm run hippy:dev
```

> For dev target, the demo project has defined a [alias to local hippy-react](./scripts/hippy-webpack.dev.js#L80), you should remove it first if you don't use it.

### Start a debug server

Keep the `hippy:dev` running and open anther terminal, and execute:

```
npm run hippy:debug
```

### Start debug with debugger

For Android, open `chrome://inspect`, `UNCHECK` the `Discover USB devices` option and `CHECK` `Discover network targets` option, click on the `Configuration` button and make sure `localhost:38989` in the list.

Then you will see the cellphone in below list, click on the `Inspect` will popup the debugger window.

For iOS we need Safari, at first need the `Develop` menu appear(`Develop` menu toggle is available in `Preference` -> `Advanced` -> `Show Develop menu in menu bar`). Then you will see the Simulator or Cellphone in the `Develop` menu, point to the device and click on the JSContext to open debugger window.

### Build the native

Build the native codes in `ios` with [Xcode](https://developer.apple.com/xcode/), or `android` with [Android Studio](https://developer.android.com/studio).

Start to run the native app after build and connect the debug server.

## Integrate the js files to native app

### Build the production js files

```
npm run hippy:vendor # Build the vendor js
npm run hippy:build # Build the index js
```

The output files will be placed at `dist/android` and `dist/ios` folders.

### Integrate built output js to native

#### iOS

```
cp dist/ios/* ../ios-demo/res/ # Copy the built js files to native.
```

### Android

```
cp dist/android/* ../android-demo/res/ # Copy the built js files to native.
```
