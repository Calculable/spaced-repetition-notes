# Implicitly Unwrapped Optional ⚠️

##  Zweck
> When you use  `String!`  you’re saying this might have a string inside, but it might have nothing at all inside – not even an empty string. However, Swift lets you use these as if they were a  `String`, as if they always  _do_  have a value, but if you try to use a nil value by accident your code will crash. This effectively lets you say “I know this  _might_  be nil, but I’m so sure it has a value that I’m willing for my program to crash if I’m wrong.”

## Zusammenfassung
- Zweck

