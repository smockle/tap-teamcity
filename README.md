[![npm](https://img.shields.io/npm/v/tap-teamcity.svg)](https://www.npmjs.com/package/tap-teamcity)
[![Build Status](https://travis-ci.org/smockle/tap-teamcity.svg?branch=master)](https://travis-ci.org/smockle/tap-teamcity)
[![Build status](https://ci.appveyor.com/api/projects/status/ms9rme11nk1a5auq?svg=true)](https://ci.appveyor.com/project/smockle/tap-teamcity)
[![Code Climate](https://codeclimate.com/github/smockle/tap-teamcity/badges/gpa.svg)](https://codeclimate.com/github/smockle/tap-teamcity)
[![Test Coverage](https://codeclimate.com/github/smockle/tap-teamcity/badges/coverage.svg)](https://codeclimate.com/github/smockle/tap-teamcity/coverage)
[![Known Vulnerabilities](https://snyk.io/test/npm/randomly/badge.svg)](https://snyk.io/test/npm/randomly)
[![Greenkeeper badge](https://badges.greenkeeper.io/smockle/tap-teamcity.svg)](https://greenkeeper.io/)

# tap-teamcity

Formats [TAP](https://testanything.org/tap-specification.html) output for TeamCity.

## Installation

Run `npm install --save-dev tap-teamcity` to add `tap-teamcity` to your project.

## Usage

### Streaming

```JavaScript
const test = require('tape')
const tapTeamCity = require('tap-teamcity')

test.createStream()
  .pipe(tapTeamCity())
  .pipe(process.stdout)
```

### CLI

**package.json**

```JSON
{
  "name": "module-name",
  "scripts": {
    "test": "tape test/**/*.js | tap-teamcity"
  }
}
```

Then run with `npm test`

**Terminal**

```
tape test/**/*.js | ./node_modules/.bin/tap-teamcity
```

## Testing

`tap-teamcity` includes several unit tests. After cloning the `tap-teamcity` repo locally, run `npm install` in the project folder to install dependencies, then `npm test` to execute the tests.

## Credits

Many thanks to @scottcorgan for creating the [tap-spec](https://github.com/scottcorgan/tap-spec) formatter, which inspired this one.
