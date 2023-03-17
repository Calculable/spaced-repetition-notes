# Never Return Type
🧨

##  Zweck
The `Never` return type is a special one in Swift, and tells the compiler that execution will never return when this function is called.

It’s used by Swift’s `fatalError()` and `preconditionFailure()` functions, both of which cause your app to crash if they are called.

The  `Never`  return type is useful because it lets Swift waive other requirements. For example, if you’re in a function that must return a value, calling a  `Never`  function means you don’t need to return anything – Swift knows you can’t return a value any more.

## Zusammenfassung
- Zweck

#learning unit#