# Naming Convention: Delegate Methods
💬

## Aufrufer
- Der Aufrufer des Delegates gibt sich immer selbst als erstes Argument mit.

## Begriffe
- In der Regel `will`, `did`, `should`

## Nur ein Argument

### Beispiele: Ohne Rückgabewert

```swift
func scrollViewDidBeginScrolling(_ scrollView: UIScrollView)
```

### Beispiele: Mit Rückgabewert

```swift
func scrollViewShouldScrollToTop(_ scrollView: UIScrollView) -> Bool
func numberOfSections(in scrollView: UIScrollView) -> Int
```

## Mehrere Argumente

> For methods that take  **additional**  arguments after the delegate’s source object, the method’s base name is the delegate’s source type  **by itself**  and the first argument is  **unlabeled.**  Then:

```swift
func tableView(
  _ tableView: UITableView,
  willDisplayCell cell: UITableViewCell,
  forRowAt indexPath: IndexPath)
```


```swift
func tableView(
  _ tableView: UITableView,
  heightForRowAt indexPath: IndexPath
) -> CGFloat
```

## Zusammenfassung
- Was ist eine gute Benennung für Delegate-Methoden?
	- Mit und ohne Rückgabewert
	- Mit einem oder mehreren Parametern


#learning unit#