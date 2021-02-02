# Webpack
## Adding polyfills

The `entry` can be used to catenate multiple files together into a single file. This is useful
when adding polyfills, since you can make the first array element the polyfill pack.

```javascript
entry: ['@babel/polyfill', path.resolve(__dirname, 'hello.jsx')],
```

