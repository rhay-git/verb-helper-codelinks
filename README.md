# verb-helper-codelinks [![NPM version](https://badge.fury.io/js/verb-helper-codelinks.svg)](http://badge.fury.io/js/verb-helper-codelinks)

> Generate a list of links to the first line of code for each method in a given directory. 

## Install with [npm](npmjs.org)

```bash
npm i verb-helper-codelinks --save
```

## Usage

Add a `verbfile.js` to your project with the following:

```js
var verb = require('verb');

// register the helper
verb.helper('codelinks', require('verb-helper-codelinks'));

// add a task to build your docs
verb.task('default', function () {
  return verb.src('my-documentation.md')
    .pipe(verb.dest('docs/'));
});
```

In your `.verb.md` file:

```markdown
{%= codelinks('lib/') %}
```

Results in markdown like this:

```markdown
+ **[one](fixtures/one.js)**
  - [.a](fixtures/one.js#L7)
  - [.b](fixtures/one.js#L13)
  - [.c](fixtures/one.js#L19)
+ **[two](fixtures/two.js)**
  - [.c](fixtures/two.js#L7)
  - [.d](fixtures/two.js#L13)
  - [.e](fixtures/two.js#L19)

_(Code links generated by Verb's [api-toc] helper)_
[api-toc]: https://github.com/jonschlinkert/api-toc
```

That renders to a list of links that looks like this:

+ **[one](fixtures/one.js)**
  - [.a](fixtures/one.js#L7)
  - [.b](fixtures/one.js#L13)
  - [.c](fixtures/one.js#L19)
+ **[two](fixtures/two.js)**
  - [.c](fixtures/two.js#L7)
  - [.d](fixtures/two.js#L13)
  - [.e](fixtures/two.js#L19)

_(Code links generated by Verb's [api-toc] helper)_
[api-toc]: https://github.com/jonschlinkert/api-toc

See the [example verbfile.js](./verbfile.js).

## Why use Verb?
It's magical and smells like a baby unicorn. Besides that, it also generates documentation. And it's magical.

## Related projects
* [template-helpers](https://github.com/jonschlinkert/template-helpers): Generic JavaScript helpers that can be used with any template engine. Handlebars, Lo-Dash, Underscore, or any engine that supports helper functions.
* [verb](https://github.com/assemble/verb): Verb makes it dead simple to generate markdown documentation, using simple templates, with zero configuration required. A project without documentation is like a project that doesn't exist.  

## Running tests
Install dev dependencies.

```bash
npm i -d && npm test
```

## Contributing
Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](https://github.com/jonschlinkert/verb-helper-codelinks/issues)

## Author

**Jon Schlinkert**
 
+ [github/jonschlinkert](https://github.com/jonschlinkert)
+ [twitter/jonschlinkert](http://twitter.com/jonschlinkert) 

## License
Copyright (c) 2015 Jon Schlinkert  
Released under the MIT license

***

_This file was generated by [verb-cli](https://github.com/assemble/verb-cli) on March 25, 2015._

[verb]: https://github.com/assemble/verb

[api-toc]: https://github.com/jonschlinkert/api-toc