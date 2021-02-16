# Dynamic content

## Adding Javascript files from JS

Create a script node, add the src attribute, and then
add it to the DOM

```javascript
const headElement = document.getElementsByTagName('head')[0]; 
const jsScript = document.createElement('script');
jsScript.setAttribute('src', 'https://example.com/file.js');
headElement.appendChild(jsScript); 
```

## Adding CSS files from JS

```javascript
const headElement = document.getElementsByTagName('head')[0]; 
const cssLink = document.createElement('link');
cssLink.setAttribute('rel', 'stylesheet');
cssLink.setAttribute('type', 'text/css');
cssLink.setAttribute('href', 'https://example.com/file.css');
headElement.appendChild(cssLink); 
```

Create a link node, add the relevant attributes, and add
it to the DOM

## Finding out when things are finished loading

```javascript
// continued from above
cssLink.addEventListener('load', (e) => {});
```