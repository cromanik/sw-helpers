<!-- To make changes, edit templates/README.hbs, not README.md! -->
[![Build Status][travis-image]][travis-url]

# Service Worker Helpers

A [collection of libraries](#the-libraries) that help enhance your existing
[service worker](http://www.html5rocks.com/en/tutorials/service-worker/introduction/)
by providing commonly-needed functionality.

A [monorepo](https://github.com/babel/babel/blob/master/doc/design/monorepo.md)
approach is used to manage multiple helper libraries, each of which is versioned
and published to `npm` independently.

## The Libraries
### sw-appcache-behavior
A service worker implementation of the behavior defined in a page&#x27;s App Cache manifest.

**Install**: `npm install --save-dev sw-appcache-behavior`

**Learn More**: [About](projects/sw-appcache-behavior) •
                [Demo](projects/sw-appcache-behavior#demo) •
                [API](projects/sw-appcache-behavior#api)

### sw-offline-google-analytics
A service worker helper library to retry offline Google Analytics requests when a connection is available.

**Install**: `npm install --save-dev sw-offline-google-analytics`

**Learn More**: [About](projects/sw-offline-google-analytics) •
                [Demo](projects/sw-offline-google-analytics#demo) •
                [API](projects/sw-offline-google-analytics#api)


## Development

### Existing Build Tasks

Tasks are run via [`gulp`](http://gulpjs.com/), and assume that you have a
globally installed `gulp` binary (`npm install -g gulp`) as well as
a locally installed set of `node_module` dependencies (`npm install` from within
the top-level directory).

When running a task, an optional `--project=project-name` parameter can be used.
For example, `gulp build:watch --project=sw-appcache-behavior`.
By default the task will be run against all projects.

### New Projects

New projects should be created as sub-directories of [projects](projects/),
following the basic layout of the existing projects. It's recommended that each
library adopts the `sw-` prefix, for consistency.

Always include the following:

- `src/` - raw source files, with [JSDoc](http://usejsdoc.org/)-formatted
comments.
- `build.js` - Should `export` a function that performs all the steps needed to
produce a ready-to-use library in local `build/` directory.
- `test/*.js` - One or more [Mocha](https://mochajs.org/) test suites.
- `package.json` - The `npm` metadata for the library. Each library is
versioned independently.

A `demo/` directory is optional but encouraged. The project's `README.md` file
will be automatically generated based on a template using the metadata found in
the `JSDoc` comments.

### External Contributions

Please read the [guide to contributing](CONTRIBUTING.md) prior to filing any
pull requests.

## License

Copyright 2016 Google, Inc.

Licensed under the [Apache License, Version 2.0](LICENSE) (the "License");
you may not use this file except in compliance with the License. You may
obtain a copy of the License at

  http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

[npm-url]: https://npmjs.org/package/sw-helpers
[npm-image]: https://badge.fury.io/js/sw-helpers.svg
[travis-url]: https://travis-ci.org/GoogleChrome/sw-helpers
[travis-image]: https://travis-ci.org/GoogleChrome/sw-helpers.svg?branch=master
