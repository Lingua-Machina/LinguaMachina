# Conditions and loops

<hr>

Conditions and loops are achieved through messages to various objects.

## Conditions
```
(i == 1337) ifTrue: { ... }
            ifFalse: { ... };

(a < b) ifTrue: { ... };

(a > b) ifFalse: { ... };
```

## Loops
```
{ # some code # } repeat;

{ # some code # } repeatTimes: 42;

{ i < 42 } whileTrue: { # some code # };

1 to: 10 each: { | i | # some code using 'i' (or not) # };

[1, 2, 3] each: { | i | # some code  using 'i' (or not) # };
```

