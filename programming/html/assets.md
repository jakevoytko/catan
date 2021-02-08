# Assets

## Deferring JS
Info from https://javascript.info/script-async-defer

You can defer JS 

```html
<script defer src="asdf.js"></script>
<script async src="asdf.js"></script>
```

These behave similarly: neither of them block page rendering.

`defer`  fetches the scripts in the background, and then executes each of them before DOMContentLoaded
`async` loads and executes a script independent of page load ordering. Dynamic scripts behave like `async` by default.