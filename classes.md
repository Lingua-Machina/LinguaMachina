# Classes

<hr>

## Example

```
Object subclass: 'Person
    instanceVars: [ 'name, 'age ];

Person class >> newWithName: name andAge: age {
    # Primary constructor #
    ^self new |> (name: name | age: age)
};

Person >> isMinor {
    ^age < 21
};

Person >> asString {
    ^name + ", " + age asString
}
```
```
Person newWithName: "Elyan Poujol" andAge: 21
    |> println
# Elyan Poujol, 21 #
```



## Getter/Setter auto generation

```
Object subclass: 'Person
    instanceVars: [ 'name, 'age ]
```
Methods are automatically created to access instance variables. In this case: ```name``` is a getter for the instance variable *name* and ```name:``` is a setter for the instance variable *name*. Same for ```age``` and ```age:```.



## Class creation syntactic sugar

Code like `Object subclass: 'Hello` don't magically pops the variable `Hello` into scope. The sub-classing messages are desugarized to `Hello := Object subclass: 'Hello'` when the class name parameter is a symbol literal.

```
Object subclass: 'Hello;  # Variable Hello is declared #

Object subclass: aString; # Cannot infer a name so no variable declared #

aName = 'MyClass;
Object subclass: aName; # Also nope (at least for now) #
```



## Method creation syntactic sugar

```
Person >> isMinor {
    ^age < 21
}
```
Could be written as:
```
Person compile: "isMinor {
    ^age < 21
}"
```



## Primitive method declaration syntactic sugar

```
MyClass :: method = 'primitiveMethod
```
Could be written as:
```
MyClass bind: 'method toPrimitive: 'primitiveMethod
```
