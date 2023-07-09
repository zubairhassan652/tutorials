# Data Sharing
in tow different ways

### Runtime level
using context package we can access runtime level data in every package and every go routines

### Package level
using global variable we can access them accross the package


# Bundling on build tags
###### TODO

# Interface mystries
Go's interface values are really a pair of pointers. When you put a concrete value into an interface value, one pointer starts pointing at the value. The second will now point to the 
implementation of the interface for the type of the concrete value. They're called the dynamic value and the dynamic type respectively - dynamic because both are set at runtime when we 
assign concrete values into an interface value.

Go interface value
This pair of pointers is the secret to how Go's interfaces work. When a method is called on an interface value, Go follows the implementation pointer to find the appropriate method and 
the value pointer to be able to use the value as the receiver (or it panics if the 'box' is empty: a nil value). Thus you can see why code that works with an interface value really cannot 
work on concrete values alone.
