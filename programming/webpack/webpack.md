# Webpack
## Adding polyfills

The `entry` can be used to catenate multiple files together into a single file. This is useful
when adding polyfills, since you can make the first array element the polyfill pack.

```javascript
entry: ['@babel/polyfill', path.resolve(__dirname, 'hello.jsx')],
```

## Command line arguments
`--entry`: This doesn't have any special recognition for files. I needed to do `./a/b.js` instead of `a/b.js`
You can specify `--entry` multiple times and the files will be catenated in that order