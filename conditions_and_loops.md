# Conditions and loops
## Conditions
```
(i == 1337) ifTrue: { ... }
            ifFalse: { ... };

(a < b) ifTrue: { ... };

(a > b) ifFalse: { ... };
```

## Loops
```
{ ... } repeat;

{ ... } repeatTimes: 42;

{ i < 42 } whileTrue: { ... };

1 to: 10 each: { :i | ... };

(1 to: 10) each: { :i | ... };
```
