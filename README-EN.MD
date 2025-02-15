
# noie.js

[![996.icu](https://img.shields.io/badge/link-996.icu-red.svg)](https://996.icu)
[![LICENSE](https://img.shields.io/badge/license-Anti%20996-blue.svg)](https://github.com/996icu/996.ICU/blob/master/LICENSE)

[中文](README.MD) | English

This is an ECMAScript Standard checking script.

It can often be used to check Internet Explorer or any old browsers.

There is no difference between IE and an old browser that can't support ES6.
So I'll call all browser that doesn't support a specified ECMAScript Standard as IE.

- [noie.js](#noiejs)
  * [Why](#why)
  * [Usage](#Usage)
    - [Auto](#automatically-detection)
    - [Manually](#manually-detection)
  * [Support List](#Support_List)
  * [noie.obfuscated.js](#what-is-noieobfuscatedjs)
  + [Copyright](#Copyright)

## Why?

Personal opinion: Supporting IE by using Bable is meaningless because it will only let IE users keep using it.
We should **stop supporting IE** to encourage people who use IE to make a change. 
It's the time to promote new technologies to people!

Oh, of course, if you are targeting government or other security sensitive scenarios, you should consider safety first, and then the new technology.

## Usage

All of these files are already minified manually by myself. You can use raw.githubusercontent.com to include the script.

### Automatically detection

I've added an auto-detection feature in the new version. 
If you'd like to use it, please import the corresponding version of the script.
For example, if I want to detect weither the browser supports ES2020 or not, you can import the script like this: 
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

### Manually detection
Manual detection is supported as well. Include the following script to your page to use it.
```html
<script src="/path/to/noie.js" />
```

Avalible function are listed in [Support List](#support-list). Here is a example for detecting ES2020.

```javascript
es2020(function() {
  alert("Unsupported browser")
})
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
- ES2025
  + Auto-detection version: `noie.es2025.js`
  + Function declaration in full version: `es2025(onFail?: () => void, onSuccess?: () => void)` 
  + Detection method: Ignore Case flag support in Regex ``` /0/i ``` 

## What is `noie.obfuscated.js`

> **Translation may differ from the Chinese version because I believe that person can't read English, so the Chinese version is mainly an explanation to him.**
> **But the English version is to explain to all readers what is happening.**



There was a random person who just came out and said my script is not opensource, and it's **obfuscated**.
It's very funny that this guy knows nothing about js.

This is **not** obfuscation! **This is minify!**

The reason I didn't provide the non-minified version is that I actually don't have one!
I did the minification with my hands without using tools like ESBuild. I first wrote it in github.dev and then manually minified it.
There is no non-minified version at first.

I know that guy may love obfuscation a lot, so I've provided an obfuscated version for that person.

For the obfuscator, it's a modified version of [this project](https://github.com/lowbyteproductions/JavaScript-Is-Weird).
I highly recommend watching his [original video](https://www.youtube.com/watch?v=sRWE5tnaxlI).

And here is the modified version: [My Gist](https://gist.github.com/Lama3L9R/16e84970e357ed77d72b3fb02d7c5fce)

In case you are actually using this obfuscated version, this is not supported anymore and will not be updated anymore.

## Copyright

OPENSOURCE UNDER LICENSE: Anti-996

Copyright (c) 2025 Qumolama.d (As known as lamadaemon)

If you want to learn more about 996 work style and anit-996, please visit: https://996.icu
