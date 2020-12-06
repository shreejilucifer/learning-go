## Cards

<br>

### Project Overview

<hr>

`newDeck` - Create a list of playing cards. Essentially an array of strings

`print` - Log out the contents of a deck of cards

`shuffle` - Shuffles all the cards in a deck

`deal` - Create a _hand_ of cards

`saveToFile` - Save a list of cards to a file on the local machine

`newDeckFromFile` - Load a list of cards from the local machine

### Variable Declarations

<hr>

`var` `card` `string` = `"Ace of Spades"`

Go has _static_ type checking

Go Basic Data Types:

- bool
- string
- int
- float64

Assignment of variables

`var card string = "Ace of Spades"`

`card := "Ace of Spades"`

### Returning Values in Functions

<hr>

```go
...
    card := newCard()
...
func newCard() string {
	return "Five of Diamonds"
}
```

### Slices and For Loops

<hr>

Array: Fixed Length list of things

Slice: An array that can grow or shrink

> Every element in a slice must be of same type.

Declaring Slice:

```go
card := []string{"Ace of Diamonds", "Five of Diamonds"}
```

Adding elements to slice:

```go
cards = append(cards, "Six of Spades")
```

For loop:

```go
for i, card := range cards {
    fmt.Println(i, card)
}
```

> - Go is not a Object Oriented Programming Language.

### Custom Type Declarations

`type deck []string`

Now the `deck` type can be used throughout the `main` package.

`cards := deck{...}`

> Run both files: go run main.go deck.go

### Receiver Function

<hr>

```go
func (d deck) print() {
	for i, card := range d {
		fmt.Println(i, card)
	}
}
```

> Use `_` to tell go that the variable is not needed. `for _, suit`

### Slice Range Syntax

<hr>

`fruits[startIndexIncluding:upToNotIncluding]`

`fruits[0:2]` OR `fruits[:2]`

Function Arguements:

`func deal(d deck, handSize int)...`

### Returning Multiple Values

<hr>

`func deal(d deck, handSize int) (deck, deck)`

### Byte Slices

<hr>

> `ioutils` package for File Management

`WriteFile` takes a parameter `[]byte` called _byte slice_, thus the string should be converted to byte (ASCII)

Type conversion in Go:

`Converting String to Byte` - `[]byte("Hi there!")`

> `strings` package for String Management

`Join` function - `strings.Join([]string(d), ",")`

`Split` function - `strings.Split(string(bs), ",")`

> `os` package for OS Management (Exiting Process)

> `error` will be `nil` if everything goes correctly

IF ELSE in Go:

```go
    if err != nil {
        ...
    }
```

> `math` package for complex mathematical operations. (`rand`)

Length of Slice:

```go
    len(d)
```

### Tests in Go

<hr>

To Test make a file ending with `_test.go` & run `go test`.

Create a new function in the test file with `Test` as prefix of function name(Just a convention)

```go
func TestNewDeck(t *testing.T) {
	d := newDeck()

	if len(d) != 16 {
		t.Errorf("Expected Deck Length of 16, but got %v", len(d))
	}
}
```
