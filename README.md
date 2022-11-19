# Template to inject components in Community Solid Server as Package

This is what worked for me, although it's possible that I'm overcomplicating things.

## How to use

- Replace all occurences of `example-module` by your module name.
- `npm install`
- `npm run build` to build.
- `npm run start` to start, using the configuration in `config/default.json`. This is where you adjust the configuration. It worked for me when splitting up CSS and my own config files (`default.json` is in my own context, and imports `css.json`, which is in the CSS context. The latter than references other CSS config files using `css:` and then the config).
- CSS exports all classes used by Component.js (referenced in config files) in its `index.ts`, so I'm doing this as well. I'm not sure if it is necessary, but it works.
- As a test, this template injects a new `DataAccessor`, for which the code was copied.

Extra tip: You can add more CLI arguments by looking at what CSS does in `config/http/server-factory/https-websockets.json`.
