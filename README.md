did-uri
=======

Decentralized Identity (DID) URI parser and formatter.

## Abstract

In this module we provide a w3 compliant interface for parsing and serializing
[Decentralized Identity (DID)](https://w3c-ccg.github.io/did-spec/) URIs
as specified by [Decentralized
Identifiers](https://w3c-ccg.github.io/did-spec/#decentralized-identifiers-dids)
specification. This module provides an interface similar to that of the
`url` module in the Node standard library.

## Installation

```sh
$ npm install did-uri
```

## Example Usage

```js
const did = require('did-uri')
const spec = did.parse('did:ara:68656c6c6f/music?key=mk706c6179206d65')
console.log(spec)
```

outputs:

```js
{ reference: 'did:ara:68656c6c6f/music?key=mk706c6179206d65',
  did: 'did:ara:68656c6c6f',
  method: 'ara',
  identifier: '68656c6c6f',
  path: '/music',
  fragment: '',
  query: 'key=mk706c6179206d65',
  param: '' }
```

## API

### `parsed = did.parse(uri)`

Parses a given DID uri and returns an object similar to a `DID`
instance.

### `formated = did.format(obj)`

Formats a given DID URI or object into a normalized formatted URI.

### `did = new DID(uri [,base])`

Parses and creates a new `DID` instance.

#### `did.reference`

A reference to the `uri` that was parsed as input.

#### `did.did`

The component of the URI containing the protocol, method, and
identifier in the form of `did:method:identifier`.

#### `did.method`

The `method` component of the URI.

#### `did.identifier`

The `identifier` component of the URI.

#### `did.param`

The `param` (;) component of the URI.

#### `did.path`

The `path` component of the URI.

#### `did.fragment`

The `fragment` (#) component of the URI.

#### `did.query`

The `query` (?) component of the URI.

#### `did.parameters`

The `param` string component of the URI parsed into an object.

#### `did.queryParameters`

The `query` string component of the URI parsed into an object.

#### `did.fragmentParameters`

The `fragment` string component of the URI parsed into an object.

## See Also

* [Decentralized Identity Spec](https://github.com/w3c-ccg/did-spec)
* [Universal Resolver](https://github.com/decentralized-identity/universal-resolver)
* [did-universal-resolver-driver](https://github.com/littlstar/did-universal-resolver-driver)
* [did-universal-resolver-resolution](https://github.com/littlstar/did-universal-resolver-resolution)


## License

MIT
