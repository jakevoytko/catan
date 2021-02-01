# Templates
## Nested templates

Templates are referred to by name, which matches the filename without directories by default.

I've been adding the full path to template by using the `define` directive when I need to disambiguate

```go
{{define "about/about.html.tmpl"}}
  <html>
    <head>
      <title>About</title>
    </head>
    <body>
      <h1>About</h1>
      <p>About me is a bunch of stuff in my room</p>
    </body>
  </html>
{{end}}
```

Then in Go code

```go
c.HTML(http.StatusOK, "about/about.html.tmpl", gin.H{})
```
## Multiple template renderers in one app

Gin's contrib orgnaization provides a multitemplate renderer that allows applications to use more than one `*template.Template`

## Recursive template rendering

child:
```html
{{define "content"}}
<h1>Goodbye, cruel world</h1>
{{end}}
```

base:
```html
<html>
    <head>
        <title>The title</title>
    </head>
    <body>
        {{template "content" .}}
    </body>
</html>
```

I found that when providing to `AddFromFiles`, I needed to add them in the order ``[base, child]``, otherwise it didn't work.