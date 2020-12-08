## Structs

<br>

Data structure. Collection of properties that are related together.

### Defining Structs

<hr>

- Define the fields the struct has
- Create a new value / Copy of the struc

Defining Structs:

```go
    type person struct {
        firstName string
        lastName string
    }
```

Declaring Structs:

```go
    alex := person{"Alex", "Anderson"}
    // OR
    alex := person{firstName: "Alex", lastName: "Anderson"}
    // OR
    var alex person
```

If using the third way of declaring, `go` will assign Zero Value to the fields by default.

`alex.firstname = "Alex"`

### Embedding Structs

<hr>

`contact contactInfo`

```go
    jim := person{
		firstName: "Jim",
		lastName: "Party",
		contact: contactInfo{
			email: "jim@gmail.com",
			zipCode: 94000,
		},
	}
```

You can also use `contactInfo` as it is in the definition rather than contact.

### Structs with Receiver Functions

<hr>

```go
func (p person) print() {
	fmt.Printf("%+v", p)
}
```

### Pointers in Go

<hr>

- `&`variable :- Gives me the memory address of the value this variable is pointing at.
- `*`pointer :- Give me the value this memory address is pointing at.

```go
    func (pointerToPerson *person) updateName(newFirstName string) {
        (*pointerToPerson).firstName = newFirstName
    }
```

Shortcut:

`jim.updateName("Jimmy")`

Gotchas:

```go
    mySlice := []string{"Hi", "There", "How", "Are", "You"}
    updateSlice(mySlice)
    // Bye There How Are You
...
    func updateSlice(s []string) {
        s[0] = "Bye"
    }
```

Slices are Reference Types
Maps are Reference Types
Funcs are Reference Types
Channels are Reference Types
