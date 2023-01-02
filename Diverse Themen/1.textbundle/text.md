
# Vaadin
- Server Side
- Java Framework

```swift
@Route(value="myhome")
public class MainView extends VerticalLayout {
    private EmployeeRepository employeeRepository;
    private EmployeeEditor editor;
    Grid<Employee> grid;
    TextField filter;
    private Button addNewBtn;
}
```

Bei der initialisierung kann man die Elemente noch genauer beschreiben. Am Ende wird das ganze zur UI hinzugefügt:

```
add(actions, grid, editor); //beachte: Add
```

## Zusammenfassung
- Zweck
- Wie ist der Code aufgebaut (nur das Konzept)