# Minimizing outputs

The easiest way that I found to minimize Webpack outputs is to use `mode: production`

```javascript
module.exports = {
    mode: isDev ? 'development' : 'production'
}
```
