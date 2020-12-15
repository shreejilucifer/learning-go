## Channels

<br>

### Project Overview

<hr>

Status Checker - To check provided urls are up or down.

### Go Routnes

<hr>

Go Routine is the package runner which compiles and runs the go program.

`Blocking Call` is a function call which takes some time (`delay`) to get executed.

`go` keyword helps running the code to a new go routine

```go
    go checkLink(link)
```

Scheduler runs `one` routine until it finishes or makes a blocking call (like an HTTP request)

By default Go tries to use one core!

Scheduler runs one thread on each "logical" core.

Concurrency - We can have multiple threads executing code. If one thread blocks, another one is picked up and worked on.

Parallelism - Multiple threads executed at the exact same time. Requires multiple CPU's.

### Channels

<hr>

`Main Routine` will end execution even if the `Child Routines` have not completed execution.

Channels are used to manage the routines.

Channels are way to communicate between different Routines.

Creating Channels:

`c := make(chan string)`

### Channel Implementation

<hr>

`channel <- 5` - Send the value '5' into this channel

`myNumber <- channel` - Wait for a value to be sent into the channel. When we get one, assign the value to 'myNumber'

`fmt.Println(<- channel)` - Wait for a value to be sent into the channel. When we get one, log it out immediately

### Blocking Channels

<hr>

```go
	for i := 0; i < len(links); i++ {
		fmt.Println(<-c)
	}
```

infinite for loop

```go
    for {
		go checkLink(<-c, c)
	}
```

OR

```go
    for l := range c {
		go checkLink(l, c)
	}
```

Sleeping a routine:

`Sleep` pauses the current goroutine

`time.Sleep(5 * time.Second)` - Pause for 5 seconds

Function Literal = Anonymous Function

```go
    go func(link string) {
        time.Sleep(5 * time.Second)
        checkLink(link, c)
    }(l)
```
