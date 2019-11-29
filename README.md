# @umijs/plugin-model

[![codecov](https://codecov.io/gh/umijs/plugin-model/branch/master/graph/badge.svg)](https://codecov.io/gh/umijs/plugin-model)
[![NPM version](https://img.shields.io/npm/v/@umijs/plugin-model.svg?style=flat)](https://npmjs.org/package/@umijs/plugin-model)
[![CircleCI](https://circleci.com/gh/umijs/plugin-model/tree/master.svg?style=svg)](https://circleci.com/gh/umijs/plugin-model/tree/master)
[![GitHub Actions status](https://github.com/umijs/plugin-model/workflows/Node%20CI/badge.svg)](https://github.com/umijs/plugin-model)
[![NPM downloads](http://img.shields.io/npm/dm/@umijs/plugin-model.svg?style=flat)](https://npmjs.org/package/@umijs/plugin-model)

Data flow solution based on hooks and umi plugin.

## Install

```bash
# or yarn
$ npm install
```

## Usage

Configure in `.umirc.js`,

```js
export default {
  plugins: [['@umijs/plugin-model', options]],
};
```

Then add model file in `src/model(s)`, add use it in your React Component like this:

```js
import React from 'react';
import { useModel } from 'umi';

export default () => {
  const yourModel = useModel('modelfilename');
  return <>{yourModel.text}</>;
};
```

Full example can find in [./example](https://github.com/umijs/plugin-model/tree/master/example)

## Plugin API

### Register extra models

Add extra models from other plugins

```js
// use custom namespace
// @@ is used for internal models
api.register('addExtraModels', () => [
  {
    absPath: join(paths.absTmpDirPath, 'init', 'user.tsx'),
    namespace: '@@user',
  },
  {
    absPath: join(paths.absTmpDirPath, 'init', 'access.tsx'),
    namespace: '@@access',
  },
])

// use default namespace
api.register('addExtraModels', () => [
  join(paths.absTmpDirPath, 'init', 'a.tsx')]),
  join(paths.absTmpDirPath, 'init', 'b.tsx')])
])
```

## LICENSE

MIT
