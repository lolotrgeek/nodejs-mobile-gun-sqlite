# nodejs-mobile-gun-sqlite

A Gun <> SQLite Adapter for native android integration via nodejs-mobile to enable long-term storage for Gun data.

## Dependencies
A nodejs-mobile implementation [setup to load from a project folder](https://github.com/JaneaSystems/nodejs-mobile-samples/tree/master/android/native-gradle-node-folder).
A node <> native bridge exposing a native SQLite implementation, a few will be added to this repo soon.

https://github.com/lolotrgeek/nodejs-mobile-android-bridge
https://github.com/lolotrgeek/nodejs-mobile-sqlite

## Installation

First setup dependencies using instructions from repos in above section.

`npm install nodejs-mobile-gun-sqlite --save` or `yarn add nodejs-mobile-gun-sqlite`.

## Run

```javascript
const Gun = require('gun')
const GunSQLite = require('gun-sqlite');
const adapter = GunSQLite.bootstrap(Gun);

const gun = new Gun({
    ...
    file: false,
    radisk: false,
    localStorage: false,
    // Defaults
    sqlite: {
        database_name: "GunDB.db",
    }
})
```

## Credits

sqlite bindings based on https://github.com/xpbrew/cordova-sqlite-express-build-support

General functionality from [gun-react-native-sqlite] (https://github.com/lolotrgeek/gun-react-native-sqlite)

For api structure from [sqlite3] (https://github.com/mapbox/node-sqlite3)