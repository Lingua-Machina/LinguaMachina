# Code examples

---

## Helloworld!

```
"Helloworld!" println
```

## Factorial

```
Int >> factorial {
	^(self == 0)
		ifTrue:  1
		ifFalse: (self * (self - 1) factorial)
};

5 factorial

# 120 #
```

## Reverse array
```
Array >> reversed {
	reversedArray := [];

	length to: 1 do: { | i |
		reversedArray add: (self getAt: i);
	};

	^reversedArray
};

[1, 2, 3] reversed

# [3, 2, 1] #
```

