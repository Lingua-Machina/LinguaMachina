# Syntax

<hr>

## Comments

```
# Hello #

# Hello
  World #
```

<hr>

## Literals

### Integers
```
1337
1234
-1
```

### Doubles
```
1.0
1.1e10
-1e10
```

### Booleans
```
true
false
```

### Strings
```
"hello everyone !"
""
"Wow\nAmazing"
```

### Chars
```
$a
$$
$_
```

### Symbols
```
'hello
'hello:world
'HowAreYouToday
```

### Nil
```
nil
```

### Arrays
```
[1, 3, "hello"]
```

### Blocks

Blocks are like closures in other languages.

```
{ | param1 param2 |
    # a block of code with params #
}

{
    # a block of code #
}
```
The return value of a block is implicitly the value of its last statement.
Declaration and assignment both have a *nil* return value.

<hr>

## Messages

Messages are similar to method calls in other languages. They are dynamically dispatched at runtime.

The syntax for message sending is similar to Kotlin's keyword arguments:

```kotlin
myCollection.add(index = 42, element = "helloworld!")
```

Is written as:

```
myCollection put: "helloworld!" at: 42
```

### Message sending

```
anObject myMessage
anotherObject aMessage: 42
yetAnotherOne aMessageWithParam1: $a withParam2: "1337"
```

We call a *message* the combination of a *selector* and its parameters values. A *message* is sent to a *receiver* (`anObject` for example).

in the example above, `aMessage: 42` is a message with a *selector* equal to `aMessage:` and with `42` as a value for the only parameter of the *selector*. The other *selectors* in this example are `myMessage` and `aMessageWithParam1:withParam2:`.

### Chaining

When chaining messages, the result of a message sent becomes the receiver of a next message.

```
anObject methodA
        |> methodB: "hello"
        |> methodC
```

In this example, the message `methodB: "hello"` is sent to the return value of `anObject methodA` and `methodC` to the result of the `methodB:` message.

### Cascading

When cascading messages, all the messages are sent to the original receiver.

```
anObject methodA
        | methodB: "hello"
        | methodC
```

Here the messages `methodA`, `methodB: "hello"` and `methodC` are all sent to `anObject`.

### Combining both

By grouping chains and cascades in parentheses we can mix them.

```
anObject methodA
        | (methodB: "hello" |> methodC)
        | (methodD |> methodE: 1337)

anotherObject methodA
        |> (methodB: "hello" | methodC)
        |> (methodD | methodE: 1337)
```

### Special messages

Special messages don't follow the syntax of regular messages for ease of use purpose.

#### Unary messages
```
-a
+b
!c
```

#### Binary messages
```
a + b
a - b
a * b
a / b
a % b

a < b
a > b
a <= b
b >= a
a == b
a != b

a && b
a || b
```

<hr>

## Statements

### Variable declaration
```
myVar := 1337
```

### Variable assignment
```
myVar = nil
```

### Local return
```
<1337
```

### Non local return
```
^1337
```

### Statements separator
When multiple statements are in a block they must 
be separated by semi-colons (**;**).
```
a := 1300;
anObject myMessage: a;
^a + 37
```
Please note that the last semi-colon is optional.

<hr>

## Conditions and loops

See [main article](conditions_and_loops.md)

<hr>

## Classes

See [main article](classes.md)

### Method declaration

```
ClassName >> methodName: argName {
    ...
}
```

### Primitive Method Declaration
```
ClassName :: methodName: argName = 'primitiveName:
```
With ***primitiveName:*** being the id of the registered primitive.
