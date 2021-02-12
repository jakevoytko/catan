# Writing rules

Rules have a declaration that is used only at analysis
time, and the declaration is hooked up to an implementation.

```starlark
def _rule_impl(ctx):
  # Rule logic goes here
  pass

my_rule = rule(
  implementation = _rule_impl,
  attrs = {
    "deps": attr.label_list(),
  }
)
```

## Declaring outputs

Side effects are all declared and executed via `ctx.actions`

```starlark
  output_directory = ctx.actions.declare_directory(ctx.label.name)
  out = ctx.actions.declare_file(ctx.label.name + "/output_file")
```

Bazel is lazy, and will not actually produce the outputs
if they're not hooked up to an executer

```starlark
# Run the webpack executable.
ctx.actions.run(
  inputs = inputs,
  outputs = [output_directory, out],
  arguments = arguments,
  executable = ctx.executable._compiler,
) 
```

`Info`s are used to declare what the method returns. It's
convention to return a `DefaultInfo` with files that were
produced by the rule, as well as any transitive dependencies
that are needed by the file

```starlark
    return DefaultInfo(files = depset[out])
```

You can also return multiple Infos

```starlark
  return [
    DefaultInfo(files = depset[out]),
    JsModuleInfo(...),
  ]
```

## Referring to labels within rule functions

I found that I had to reference them in the declaration
and access them via ctx. I don't know if that's always true

```starlark
def _rule_impl(ctx):
  ctx.attr._polyfill

react_binary = rule(
  attrs = {
    # ///
    "_polyfill": attr.label(default = Label("@npm//@babel/polyfill")), 
  }
)
```