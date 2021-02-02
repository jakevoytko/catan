# GraphiQL
Pronounced "graphical"

## Customizing

This is going to change with GraphiQL 2, but the GraphiQL object has fields that can be overridden with
custom React components

```javascript
import GraphiQL from 'graphiql';

const Logo = () =><span>{'LOGO'}</span>;
GraphiQL.Logo = Logo;

constApp = () => (
    // Construct with the Logo component
    <GraphiQL ... />
);
```

## Loading

GraphiQL is sensitive to load order between CSS and JS. 

```go
<link rel="stylesheet" href="https://unpkg.com/graphiql/graphiql.min.css" />
<script src="assets/js/graphiql.bundle.js"></script>
```

`graphiql.bundle.js` is a custom application that contains GraphiQL. I had these lines switched
previously, and this loaded a broken GraphiQL in Chrome.