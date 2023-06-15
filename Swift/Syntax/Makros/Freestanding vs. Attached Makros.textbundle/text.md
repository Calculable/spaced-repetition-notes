# Freestanding vs. Attached Makros
⚙️

##  Freestanding

```swift
#assert(max(a, b) == c)
```

## Attached

```swift
@CaseDetection
enum Path {
    case relative(String)
    case absolute(String)
}
```

=\> Solche Makros lesen den geschriebenen Code und generieren weiteren Code dazu.

## Zusammenfassung
- Unterschied (Syntax)

#Swift5.9# #learning unit#