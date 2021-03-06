# ShaderViewer [![npm][npm-image]][npm-url] [![runkit][runkit-image]][runkit-url]
Preprocess and format the shader code.

### Feature
* Preprocess directives,  ```#define```, ```#if```, ```#elif```, ```#endif```, ```#if defined``` ... 
* Remove unused function, struct...
* Format

### Chrome Extensions
[Chrome Extensions.crx](https://github.com/06wj/shaderViewer/blob/dev/extensions.crx?raw=true)  
This extension can automatically detect the shader of the current page, then preprocess and show it in the panel.

### Online Demo
[https://06wj.github.io/shaderViewer/demo/](https://06wj.github.io/shaderViewer/demo/)

![](https://gw.alicdn.com/tfs/TB1lkmzuL1TBuNjy0FjXXajyXXa-1170-1254.png_600x600.jpg)

### Module Usage
* import modules
  ```
  const compiler = require('shader-compiler').compiler;
  const shake = require('shader-compiler').shake;
  ```

* set the ```options```
  ```
  const options = {
      removeUnused: true,
      ignoreConstantError: true
  };
  ```

* preprocess the code
  ```
  compiler.preprocess(code, function(error, result){  

  }, options);
  ```

* parse: preprocess => shake => format => result
  ```
  compiler.parse(code, function(error, result){  

  }, options);
  ```

* parseHighlight: preprocess => shake => format => hightlight => result

  ```
  compiler.parseHighlight(code, function(error, result){
  
  }, options);
  ```

* shake the code( code must be preprocessed )
  ```
  shake.shake(code, {function:true, struct:true});
  ```

### Dev
* run `npm install` to install dependencies
* run `npm run dev` to watch and develop
* run `npm run build` to build

### License
[MIT License](http://en.wikipedia.org/wiki/MIT_License)


[npm-image]: https://img.shields.io/npm/v/shader-compiler.svg?style=flat-square
[npm-url]: https://www.npmjs.com/package/shader-compiler
[runkit-image]: https://badge.runkitcdn.com/shader-compiler.svg
[runkit-url]: https://npm.runkit.com/shader-compiler
