# Lingua Machina

## Syntax
<hr>

### Comments

```
# Hello #

# Hello
  World #
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
```

#### Symbols
```
'hello
'hello:world
'HowAreYouToday
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
    # a block of code with params #
}

{
    # a block of code #
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
            |> methodC)
        | (methodD
            |> methodE: 1337)

anotherObject methodA
        |> (methodB: "hello" 
            | methodC)
        |> (methodD
            | methodE: 1337)
```

#### String representation of selectors
```
anObject myMessage                 # myMesage      #
anotherObject aMessageWith: param  # aMessageWith: #
yeet param1: $a param2: "1337"     # param1:param2 #
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

### Statements

#### Variable declaration
```
myVar := 1337
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

#### Statements separator
When multiple statements are in a block they must 
be separated by semi-colons (**;**).
```
a := 1300;
anObject myMessage: a;
^a + 37
```
Please note that the last semi-colon is optional.

<hr>

#### Method declaration
```
ClassName >> methodName: arg {
    ...
}
```

#### Primitive Method Declaration
```
ClassName :: methodName: arg = 'primitiveName:
```
With ***primitiveName:*** being the id of the registered primitive.
