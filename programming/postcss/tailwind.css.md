# Tailwind.css


Using this for my new project.

## Moving the config file
I don't like having config files in my project root if the server isn't
a node.js server, and you can move the config file using…

```javascript
// postcss.config.js
module.exports = {
  plugins: {
    'autoprefixer': {},
    'tailwindcss': {
      config: './homepage/tailwind.config.js',
    },
  },
}
```

## Adding styles
```javascript
// tailwind.config.js
module.exports = {
    theme: {
        extend: {
            minHeight: {
                '96': '24 rem',
            }
        }
    }
}
```

Note this is in `extend`. If `minHeight` were a sibling of `extend`, none of the prewritten
`min-h-*` would exist.