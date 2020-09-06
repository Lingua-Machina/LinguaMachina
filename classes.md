### Classes
```
Object subclass: 'Person
    instanceVars: [ 'name, 'age ];

Person class >> newWithName: name andAge: age {
    # Primary constructor #
    ^self new
        |> (name: name
            | age: age)
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