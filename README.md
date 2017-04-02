# rn-boilerplate

1. Follow guide on how to setup Android/IOS https://facebook.github.io/react-native/docs/getting-started.html 
2. `$ npm install`
3. `$ react-native run-android`

## Whats this boilerplate includes
1. Login page
2. Authentication flow
3. Using AsyncStorage to store session
4. Drawer (side menu)
5. Routing
6. API mock
7. Splash screen

## Using new react native container
1. Create new react native project
```
$ react-native init <project-name>
$ cd <project-name>
```
2. Copy the whole src folders
```
$ cp -R <rn-boilerplate-dir>/src .
```
3. Copy index.android.js and index.ios.js
```
$ cp <rn-boilerplate-dir>/index.android.js .
$ cp <rn-boilerplate-dir>/index.ios.js .
```
Note: Edit both file and rename the project name
4. Add required dependencies
```
$ npm install --save react-native-drawer
$ npm install --save react-native-router-flux
$ npm install --save react-native-snackbar
$ npm install --save react-redux
$ npm install --save redux
$ npm install --save redux-logger
$ npm install --save redux-thunk
$ npm install --save react-native-vector-icons
$ npm install --save react-native-onesignal
```
5. Link
```
$ react-native link
```
6. Run
```
$ react-native run-android
```

## One signal configuration
1. Set gradle properties
```
RN_BOILERPLATE_ONESIGNAL_APP_ID=xxxx
```

## Release configuration
1. Create release keys - https://facebook.github.io/react-native/docs/signed-apk-android.html 
2. Set gradle properties
```
RN_BOILERPLATE_RELEASE_STORE_FILE=rn-boilerplate-release-key.keystore
RN_BOILERPLATE_RELEASE_KEY_ALIAS=rn-boilerplate-key-alias
RN_BOILERPLATE_RELEASE_STORE_PASSWORD=password
RN_BOILERPLATE_RELEASE_KEY_PASSWORD=password
```

## Architecture convention
1. module's actions/states/components are shareable
  - scene MAY use module's actions/states/components
  - module MAY use other module's actions/states/components
2. scene's actions/states/components are not shareable
  - scene should NEVER use other scene's actions/states/components
  - module should NEVER use scene's actions/states/components
3. container is where to connect actions/states
4. component's job should only be for rendering
5. try not to use internal state at all