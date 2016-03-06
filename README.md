# react-native-css (and SCSS) + react-native-extended-stylesheet [![Circle CI](https://circleci.com/gh/sabeurthabti/react-native-css.svg?style=svg&circle-token=a140907997e6a37c6c5ec75f04e8150cef049ff6)](https://circleci.com/gh/sabeurthabti/react-native-css) [![NPM](https://img.shields.io/npm/dm/react-native-css.svg?style=flat-square)](https://www.npmjs.com/package/react-native-css)

 React-native-css turns valid CSS/SASS into the Facebook subset of CSS.

 This is a forked version, it seems to be work fine with [react-native-extended-stylesheet](https://github.com/vitalets/react-native-extended-stylesheet)

## Install

Global :

```bash
npm install guillaumearm/react-native-css -g
```

Requirements for your react-native project :

```bash
npm install --save react-native-extended-stylesheet
```

# Command Line Interface

React-native-css comes with a cli and you can watch a file and compile it.

``` shell
# example 1
react-native-css -i INPUT_CSS_FILE -o OUTPUT_JS_FILE --watch
```

``` shell
# example 2
react-native-css -i INPUT_CSS_FILE -o OUTPUT_JS_FILE --watch --pretty
```

``` shell
# example 3
react-native-css INPUT_CSS_FILE OUTPUT_JS_FILE -w
```

``` shell
react-native-css -i style.css -o style.js -w
```

Flags
- "-w" or "--watch" - watch for changes and recompile.
- "-i" takes a input (optional)
- "-o" takes an output path (optional)
- "-p" or "--pretty" - pretty print the resulting compiled output

## Screenshot

![the workflow](http://i.imgur.com/i2OdwiY.png)

# Example

Given the following CSS:

``` css
description {
  margin-bottom: 20;
  font-size: 18;
  text-align: center;
  color: #656656;
}

container {
  padding: 30;
  margin-top: 65;
  align-items: center;
}

```

React-native-css will generate to the following:

``` javascript
// style.js
module.exports = require('react-native').StyleSheet.create(
  {"description":{"marginBottom":20,"fontSize":18,"textAlign":"center","color":"#656656"},"container":{"padding":30,"marginTop":65,"alignItems":"center"}}
  );
```

# Usage
```js
// require the generated style file
var styles = require('./style.js')
 //{"description":{"marginBottom":20,"fontSize":18,"textAlign":"center","color":"#656656"},"container":{"padding":30,"marginTop":65,"alignItems":"center"}}


class SearchPage extends Component {
  render() {
    return (
      <View style={styles.container}>
        <Text style={styles.description}>
        Buy
        </Text>

      </View>
    );
  }
}

```
