# io-cep [![Build Status](https://travis-ci.org/lagden/io-cep.svg?branch=master)](https://travis-ci.org/lagden/io-cep)

> Search address using zip code through Correios's form

## Install

```
$ npm install --save io-cep
```


## Usage

```js
var consulta = require('io-cep');

consulta('01310-940')
  .then(function(res){
    if(res.success) {
      process.stdout.write(res.logradouro + '\n');
      //=> Avenida Paulista
    } else {
      process.stdout.write(res.message + '\n');
      //=> CEP not found or parse error.
    }
  })
  .catch(function(err){
    process.stdout.write(err.message + '\n');
    //=> CEP must be a string
  });
});
```


## API

### consulta(cep)

#### cep

*Required*  
Type: `string`

CEP of the address desired.


## CLI

#### Install

**io-cep** works well with standard input.

```
$ npm install -g io-cep
```

#### Usage

```
$ io-cep 01310-940
```


## Dev

The code was written in ES6 and converted to ES5 
via [babel](https://babeljs.io/).

### Build

```
$ npm test; npm run build
```

After transpiled, the refinement is done in hand.


## License

MIT © [Thiago Lagden](http://lagden.in)
