# Compass Query Bar [![][workflow_img]][workflow_url]

> Renders a component for executing MongoDB queries through a GUI.

## License

Apache 2.0

## Usage

### Browser

Setting values via configure:

```js
import Plugin, { configureStore, configureActions } from '@mongodb-js/compass-query-bar';

const actions = configureActions();
const store = configureStore({
  localAppRegistry: appRegistry,
  actions: actions,
  namespace: 'db.coll',
  serverVersion: '4.2.0',
  fields: [],
});

<Plugin store={store} actions={actions} />
```

### Hadron/Electron

```js
const role = appRegistry.getRole('Query.QueryBar')[0];
const Plugin = role.component;
const configureStore = role.configureStore;
const configureActions = role.configureActions;

const actions = configureActions();
const store = configureStore({
  globalAppRegistry: appRegistry,
  localAppRegistry: localAppRegistry,
  actions: actions,
  namespace: 'db.coll',
  serverVersion: '4.2.0',
  fields: []
});

<Plugin store={store} actions={actions} />
```

### Fields

The fields array must be an array of objects that the ACE editor autocompleter understands. See
[This example](https://github.com/mongodb-js/ace-autocompleter/blob/master/lib/constants/accumulators.js)
for what that array looks like.

[workflow_img]: https://github.com/mongodb-js/compass-query-bar/workflows/Check%20and%20Test/badge.svg?event=push
[workflow_url]: https://github.com/mongodb-js/compass-query-bar/actions?query=workflow%3A%22Check+and+Test%22
