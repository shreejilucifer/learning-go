## Maps

<br>

Declaring Maps :-

```go
    colors := map[string]string{
		"red": "#ff0000",
		"green": "#00ff00",
	}
```

```go
    var colors map[string]string
```

```go
    colors := make(map[string]string)

    colors["white"] = "#ffffff"
```

Deleting a key in Map :-

```go
    delete(colors, "white")
```

Iterating over Maps :-

```go
func printMap(c map[string]string) {
	for color, hex := range c {
		fmt.Println("Hex code for", color, "is", hex)
	}
}
```
