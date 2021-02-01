# Interfaces

## Ensuring that a type implements an interface

```go
// Define the type normally
type MyType struct{}

func NewMyType() *MyType {
    return &MyType{}
}

// Right below the definition, declare a private variable of the interface type
var assertInterface InterfaceType = NewMyType()
```

This feels like it'd be controversial (Go interfaces gain a ton of flexibility by not requiring types to,
be colocated with the interfaces that they implement), but IMO sometimes it's important that a
type implement a specific interface, and that I'd rather there be a compilation failure as close to
the `MyType` definition as possible.
