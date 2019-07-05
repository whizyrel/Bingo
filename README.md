# Bingo

A wrapper for around jwt; It forms a link with JWT token

I sincerely apologize for the troubles and I'm glad to announce that this version is now stable and functional. I really do not have time to write readmes but support and contributions are welcome.

## Installation

Use the package manager [npm](https://www.npmjs.com/package/jwt-linker) to install jwt-linker.

```bash
npm install jwt-linker
```

## Usage

```js
const jwtLinker = require('jwt-linker');
```

#### form

Use the `form` method if you would like to get a link. This method receives a number of parameters:

```js
// jwt options (an object): payload, key, options. These are normal jwt stuffs
const jwtOptions = {
  payload: payload,
  key: `key`,
  options: options,
};

// URL Options (object): mode, name, protocol like so:
const urlOptions = {
  mode: 'param' || 'query',
  name: 'requred if query mode is preferred',
  protocol: 'http' || 'https',
};

// URL (string): an example is `localhost:4200`
const URL = localhost:4200;

jwtLinker.form(jwtOptions, urlOptions, URL);
```

other parameters `queryName && protocol` are optional

#### jwtSign

```js
jwtLinker.jwtSign(); // signs the token
```

#### create

Use the `create` method if you would like just the encryption like so:

```js
jwtLinker.create({
  payload: payload, // JWT payload
  key: key, // encryption key
  options: options, // JWT options
});
```

#### encryptedLink

Use this method to get a link with the encryption given the configuration parameters you have supplied.

```js
jwtLinker.encryptedLink(); // returns an encrypted link based on the parameters described above in jwtLinker.form(parameters);
```

#### token

Token is a getter that returns the JWT Token.

```js
jwtSign().token; // would return the token

jwtLinker.create(parameters).token; // JWT token
```

---

## Fixes

- malformed link

---

## Additions

- method jwtSign (chainable)
- A readme
