
# noie.js

[![996.icu](https://img.shields.io/badge/link-996.icu-red.svg)](https://996.icu)
[![LICENSE](https://img.shields.io/badge/license-Anti%20996-blue.svg)](https://github.com/996icu/996.ICU/blob/master/LICENSE)

[中文](README.MD) | English

This is an ECMAScript Standard checking script.

It can often be used to check Internet Explorer or any old browsers.

There is no difference between IE and an old browser that can't support ES6.
So I'll call all browser that doesn't support a specified ECMAScript Standard as IE.

- [noie.js](#noiejs)
  * [Usage](#Usage)
  * [Support List](#Support_List)
  + [Copyright](#Copyright)

## Usage

I've added an auto-detection feature in the new version. 
If you'd like to use it, please import the special version of the script with the example below.
```html
<script src="/path/to/noie.<version>.js" />
```

For example, if I want to detect weither the browser supports ES2020 you can import the script like this: 
```html
<script src="/path/to/noie.es2020.js" />
```

After the detection process, the script will decorate the `document` object by adding a new varible `NOIE_PASS` to it.
You can find out if the standard is supported by using `if ` statements directly.
The following example will alert the user if their browser doesn't support ES2020.

```html
<script src="/path/to/noie.es2020.js" />
<script>
if (!document['NOIE_PASS']) {
  alert("Unsupported browser! Please update your browser to latest version!")
}
</script>
```

## Support List

- ES2015 (ES6)
  + Auto-detection version: `noie.es2015.js`
  + Function declaration in full version: `es6(onFail?: () => void, onSuccess?: () => void)` 
  + Detection method: Template literals ``` `a`; ``` 
- ES2016 (ES7)
  + Auto-detection version: `noie.es2016.js`
  + Function declaration in full version: `es2016(onFail?: () => void, onSuccess?: () => void)` 
  + Detection method: Exponential operator ``` 0**0; ``` 
- ES2017
  + Auto-detection version: `noie.es2017.js`
  + Function declaration in full version: `es2017(onFail?: () => void, onSuccess?: () => void)` 
  + Detection method: Async arrow functions ``` async()=>0; ``` 
- ES2018
  + Auto-detection version: `noie.es2018.js`
  + Function declaration in full version: `es2018(onFail?: () => void, onSuccess?: () => void)` 
  + Detection method: Spread operator ``` {...{}}; ``` 
- ES2019
  + Auto-detection version: `noie.es2019.js`
  + Function declaration in full version: `es2019(onFail?: () => void, onSuccess?: () => void)` 
  + Detection method: new try-catch syntax ``` try{}catch{}; ``` 
- ES2020
  + Auto-detection version: `noie.es2020.js`
  + Function declaration in full version: `es2020(onFail?: () => void, onSuccess?: () => void)` 
  + Detection method: Nullish coalescing operator ``` 0??1; ``` 
- ES2021
  + Auto-detection version: `noie.es2021.js`
  + Function declaration in full version: `es2021(onFail?: () => void, onSuccess?: () => void)` 
  + Detection method: Numeric separators ``` 1_0; ``` 
- ES2022
  + Auto-detection version: `noie.es2022.js`
  + Function declaration in full version: `es2022(onFail?: () => void, onSuccess?: () => void)` 
  + Detection method: indices flag support in Regex ``` /0/d ``` 
- ES2023
  + Auto-detection version: `noie.es2023.js`
  + Function declaration in full version: `es2023(onFail?: () => void, onSuccess?: () => void)` 
  + Detection method: new function on Array ``` Array.findLast ``` 
- ES2024
  + Auto-detection version: `noie.es2024.js`
  + Function declaration in full version: `es2024(onFail?: () => void, onSuccess?: () => void)` 
  + Detection method: unicodeSets flag support in Regex ``` /0/v ``` 

## Copyright

OPENSOURCE UNDER LICENSE: Anti-996

Copyright (c) 2022 Qumolama.d

If you want to learn more about 996 work style and anit-996, please visit: https://996.icu
