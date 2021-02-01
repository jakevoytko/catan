# Templates
## Nested templates

Templates are referred to by name, which matches their 

I've been adding the full path to template by using the `define` directive to pick a name.

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
