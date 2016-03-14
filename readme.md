<img src="assets/vuejs.png" alt="VueJS Logo" width="200" height="200"/>

# VueJS Locale<br/>![Downloads][npm-version-img] ![Downloads][npm-downloads-img] [![Build Status][ci-img]][ci] ![Dependencies][deps-img] [![Code Climate][climate-img]][climate]

[VueJS] Plugin for advanced localization of web applications.

[VueJS]: https://github.com/vuejs/vue
[ci-img]:  https://travis-ci.org/sebastian-software/vue-locale.svg
[ci]:      https://travis-ci.org/sebastian-software/vue-locale
[deps-img]: https://david-dm.org/sebastian-software/vue-locale.svg
[climate-img]: https://codeclimate.com/github/sebastian-software/vue-locale/badges/gpa.svg
[climate]: https://codeclimate.com/github/sebastian-software/vue-locale
[npm]: https://www.npmjs.com/package/vue-locale
[npm-downloads-img]: https://img.shields.io/npm/dm/vue-locale.svg
[npm-version-img]: https://img.shields.io/npm/v/vue-locale.svg



## Links

- [GitHub](https://github.com/sebastian-software/vue-locale)
- [NPM](https://www.npmjs.com/package/vue-locale)


## Installation

Should be installed locally in your project source code:

Installation via JSPM:

```bash
jspm install npm:vue-locale
```

Alternatively you can also use plain old NPM:

```bash
npm install vue-locale --save
```

## Integration

Inside your VueJS application you have to register the `VueLocale` plugin:

```js
import VueLocale from "vue-locale";

Vue.use(VueLocale,
{
  language: SELECTED_LANGUAGE,
  currency: SELECTED_CURRENCY,
  messages: MESSAGE_TEXTS
})
```

While these are typical examples of values:

- `SELECTED_LANGUAGE`: `"de"`, `"en"`, `"fr"`, ... (any valid language identifier)
- `SELECTED_CURRENCY`: `"EUR"`, `"USD"`, ... (any valid currency from [CLDR data](http://www.currency-iso.org/dam/downloads/lists/list_one.xml))
- `MESSAGE_TEXTS`: `{ key : value, ...}`


## Usage

### Adding Messages

You should pass the matching locale data structure with relevant messages e.g. German.

```js
let messages =
{
  "my-message-identifier": "Hallo Welt!",
  "my-html-identifier": "Hallo <b>Welt</b>!",
  "my-personal-identifier": "Hallo {name}!",
  ...
}
```

### Translating messages using VueJS filter

- Plain Text: ```{{ "my-message-identifier" | format-message }}```
- HTML Output: ```{{{ "my-html-identifier" | format-message }}}```
- Personal: Not possible because we can't pass the required additional data structure to the filter

### Translating using function calls

- Plain Text: ```{{ $formatMessage("my-message-identifier") }}```
- HTML Output: ```{{{ $formatMessage("my-html-identifier") }}}```
- Personal: `{{{ $formatMessage("my-personal-identifier", { name : screenName }) }}}`


### Formatting Numbers

- Number Formatting: ```{{ 3.14159 | format-number }}``` => `"3,14"`
- Percent Formatting: ```{{ 0.64 | format-percent }}``` => `"64%"`
- Currency Formatting: ```{{ 21.30 | format-currency }}``` => `"31 €"`
- Precise Currency Formatting: ```{{ 3.14 | format-currency-precise }}``` => `"31,30 €"`


### Formatting Dates



### Formatting Relative Dates





## Copyright

<img src="assets/sebastiansoftware.png" alt="Sebastian Software GmbH Logo" width="250" height="200"/>

Copyright 2015-2016<br/>[Sebastian Software GmbH](http://www.sebastian-software.de)

