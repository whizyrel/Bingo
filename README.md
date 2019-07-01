# Bingo

A wrapper for around jwt; creates a link and stuffs

I sincerely apologize for the troubles and I'm glad to announce that this version is now stable and functional. I really do not have time to write readmes but support and contributions are welcome.

To begin:
const jwtLinker = require('jwt-linker');

Use the `form` method if you would like to get a link. This method receives a number of parameters:

- jwt options (object): payload, key, options. These are normal jwt stuffs like so:
  {
  payload: payload,
  key: `preferred key`,
  options: options,
  }

- URL Options (object): mode, name, protocol like so:
  {
  mode: 'param' || 'query',
  name: 'requred if query mode is preferred',
  protocol: 'http' || 'https'
  }

- URL (string): an example is `localhost:4200`

example:
jwtLinker.form({
payload: payload,
key: `preferred key`,
options: options,
}, {
mode: 'param' || 'query',
name: 'requred if query mode is preferred',
protocol: 'http' || 'https'
}, URL);

- other parameters are optional

`jwtSign method`
`jwtLinker.jwtSign`
jwtLinker.jwtSign() // signs the token
You could do jwtSign().token // would return the token

---

`jwt.create`
Use the `create` method if you would like just the encryption like so:

jwtLinker.create({
payload: payload,
key: key,
options: options,
});

---

`jwtLinker.token`
Token
Token is a getter that returns the JWT Token.

jwtLinker.create(parameters).token // JWT token ||
jwtLinker.form(parameters).token

`jwtLinker.encryptedLink`
jwtLinker.encryptedLink() // return an encrypted link based on the parameters described above in jwtLinker.form(parameters);

---

fixes:

- malformed link

additions

- method jwtSign (chainable)
