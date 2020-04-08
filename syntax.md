# Lingua Machina

## Syntax
<hr>

### Comments

```
# Hello

# Hello
# World
```

<hr>

### Literals

#### Integers
```
1337
1234
-1
```

#### Doubles
```
1.0
1.1e10
-1e10
```

#### Booleans
```
true
false
```

#### Strings
```
"hello everyone !"
""
"Wow\nAmazing"
```

#### Chars
```
$a
$$
$_
$ 
```

#### Symbols
```
'hello
'hello:world
'HowAreYouToday?
```

#### Nil
```
nil
```

#### Arrays
```
[1, 3, "hello"]
```

#### Blocks

```
{ :param1 :param2 |
    # a block of code
}

{
    # a block of code with params
}
```

<hr>

### Messages

#### Sending
```
anObject myMessage
anotherObject aMessageWith: param
yeet param1: $a param2: "1337"
```

#### Chaining
```
anObject methodA
        |> methodB: "hello"
        |> methodC
```

#### Cascading
```
anObject methodA
        | methodB: "hello"
        | methodC
```

#### Combining both
```
anObject methodA
        | (methodB: "hello" 
            |> methodB')
        | (methodC
            |> methodD: 1337)

anotherObject methodA
        |> (methodB: "hello" 
            | methodB')
        |> (methodC
            | methodD: 1337)
```

#### Representation
```
anObject myMessage                 # myMesage
anotherObject aMessageWith: param  # aMessageWith:
yeet param1: $a param2: "1337"     # param1:param2
```

#### Special messages

##### Unary messages
```
-a
+b
!c
```

##### Binary messages
```
1 + 2
2 - 3
3 * 4
4 / 5
5 % 6
```

<hr>

### Statements

#### Variable declaration
```
let myVar = 1337
```

#### Variable assignment
```
myVar = nil
```

#### Message passing
```
anObject hello: 'world
```

#### Local return
```
<1337
```

#### Non local return
```
^1337
```

<hr>

### Classes
```
Object subclass: 'Person
    instanceVars: [ 'name, 'age ]

Person class>>newWithName: name andAge: age {
    # Primary constructor
    ^self new
        |> (name: name
            | age: age)
}

Person>>isMinor {
    ^age < 21
}

Person>>asString {
    ^name + ", " + age asString
}
```
```
Person newWithName: "Elyan Poujol" andAge: 21
    |> println
# Elyan Poujol, 21
```

#### Getter/Setter auto generation
```
Object subclass: 'Person
    instanceVars: [ 'name, 'age ]
```
Methods are automatically created to access instance variables. In this case: ```name``` is a getter for the instance variable *name* and ```name:``` is a setter for the instance variable *name*. Same for ```age``` and ```age:```.

#### Method creation syntactic sugar
```
Person>>isMinor {
    ^age < 21
}
```
Maps to:
```
Person compile: "isMinor {
    ^age < 21
}"
```
