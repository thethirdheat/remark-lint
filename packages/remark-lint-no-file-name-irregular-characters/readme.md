<!--This file is generated-->

# remark-lint-no-file-name-irregular-characters

[![Build][build-badge]][build]
[![Coverage][coverage-badge]][coverage]
[![Downloads][downloads-badge]][downloads]
[![Size][size-badge]][size]
[![Sponsors][sponsors-badge]][collective]
[![Backers][backers-badge]][collective]
[![Chat][chat-badge]][chat]

Warn when file names contain irregular characters: characters other than
alphanumericals (`a-zA-Z0-9`), hyphen-minus (`-`), and dots (`.`, full
stops).

Options: `RegExp` or `string`, default: `'\\.a-zA-Z0-9-'`.

If a string is given, it will be wrapped in
`new RegExp('[^' + preferred + ']')`.

Any match by the wrapped or given expressions creates a message.

## Presets

This rule is included in the following presets:

| Preset | Setting |
| ------ | ------- |
| [`remark-preset-lint-markdown-style-guide`](https://github.com/remarkjs/remark-lint/tree/master/packages/remark-preset-lint-markdown-style-guide) |  |

## Example

##### `plug-ins.md`

###### Out

No messages.

##### `plugins.md`

###### Out

No messages.

##### `plug_ins.md`

###### Out

```text
1:1: Do not use `_` in a file name
```

##### `plug ins.md`

###### Out

```text
1:1: Do not use ` ` in a file name
```

##### `README.md`

When configured with `'\\.a-z0-9'`.

###### Out

```text
1:1: Do not use `R` in a file name
```

## Install

[npm][]:

```sh
npm install remark-lint-no-file-name-irregular-characters
```

## Use

You probably want to use it on the CLI through a config file:

```diff
 ...
 "remarkConfig": {
   "plugins": [
     ...
     "lint",
+    "lint-no-file-name-irregular-characters",
     ...
   ]
 }
 ...
```

Or use it on the CLI directly

```sh
remark -u lint -u lint-no-file-name-irregular-characters readme.md
```

Or use this on the API:

```diff
 var remark = require('remark');
 var report = require('vfile-reporter');

 remark()
   .use(require('remark-lint'))
+  .use(require('remark-lint-no-file-name-irregular-characters'))
   .process('_Emphasis_ and **importance**', function (err, file) {
     console.error(report(err || file));
   });
```

## Contribute

See [`contributing.md`][contributing] in [`remarkjs/.github`][health] for ways
to get started.
See [`support.md`][support] for ways to get help.

This project has a [Code of Conduct][coc].
By interacting with this repository, organisation, or community you agree to
abide by its terms.

## License

[MIT][license] © [Titus Wormer][author]

[build-badge]: https://img.shields.io/travis/remarkjs/remark-lint/master.svg

[build]: https://travis-ci.org/remarkjs/remark-lint

[coverage-badge]: https://img.shields.io/codecov/c/github/remarkjs/remark-lint.svg

[coverage]: https://codecov.io/github/remarkjs/remark-lint

[downloads-badge]: https://img.shields.io/npm/dm/remark-lint-no-file-name-irregular-characters.svg

[downloads]: https://www.npmjs.com/package/remark-lint-no-file-name-irregular-characters

[size-badge]: https://img.shields.io/bundlephobia/minzip/remark-lint-no-file-name-irregular-characters.svg

[size]: https://bundlephobia.com/result?p=remark-lint-no-file-name-irregular-characters

[sponsors-badge]: https://opencollective.com/unified/sponsors/badge.svg

[backers-badge]: https://opencollective.com/unified/backers/badge.svg

[collective]: https://opencollective.com/unified

[chat-badge]: https://img.shields.io/badge/join%20the%20community-on%20spectrum-7b16ff.svg

[chat]: https://spectrum.chat/unified/remark

[npm]: https://docs.npmjs.com/cli/install

[health]: https://github.com/remarkjs/.github

[contributing]: https://github.com/remarkjs/.github/blob/master/contributing.md

[support]: https://github.com/remarkjs/.github/blob/master/support.md

[coc]: https://github.com/remarkjs/.github/blob/master/code-of-conduct.md

[license]: https://github.com/remarkjs/remark-lint/blob/master/license

[author]: https://wooorm.com
