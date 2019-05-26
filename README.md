# rtlcss loader for webpack

Work just like **[css-loader](https://github.com/webpack/css-loader)** and use **[rtlcss](https://github.com/MohammadYounes/rtlcss/)** to RTLify your css.

## installation

`npm i rtlcss-loader -D`

## Usage

[Documentation: Using loaders](http://webpack.github.io/docs/using-loaders.html)

```javascript
module.exports = {
  module: {
    loaders: [
      {
        test: /\.css$/,
        loaders: ['style', 'rtlcss']
      }
    ]
  }
};
```

for SASS/LESS you'll need **[sass-loader](https://github.com/jtangelder/sass-loader)** first :

```javascript
module.exports = {
  module: {
    loaders: [
      {
        test: /\.scss$/,
        loaders: ['style', 'rtlcss', 'sass']
      }
    ]
  }
};
```

## IMPORTANT

if you want to use [rtlcss directives](http://rtlcss.com/learn/usage-guide/control-directives/) such as `/*rtl:ignore*/` make sure you are using it as a SPECIAL comment by adding `!` before your comment.

❌ for example :

```css
div {
  /*rtl:ignore*/
  margin: -25px -25px 0 0;
}
```

✔ must be :

```css
div {
  /*!rtl:ignore*/
  margin: -25px -25px 0 0;
}
```

## License

MIT (http://www.opensource.org/licenses/mit-license.php)
