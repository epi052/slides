# Object references and mutations

## Object references and mutations

What will be the value of `a` at the end of this code?

```py
a = [1, 2, 3]
b = a
b.append(4)
```

## Object references and mutations

An assignment (e.g. `b = a`) assigns a new (additional) name to an object.

The object in the background is the same.

## Object references and mutations

If the original should remain intact it may be copied or a mutated version can be newly created based on it:

```py
a = [1, 2, 3]
# creating a new copy
b = a.copy()
# modifying b
b.append(4)
```

```py
a = [1, 2, 3]
# creating a new object b based on a
b = a + [4]
```

## Mutations

Some objects can be mutated (changed) directly - e.g. via `.append()`, `.push()`, ...

Examples: `list`, `dict`

Many simple objects are immutable after they have been created. However, they can be replaced by other objects.

Examples: `int`, `float`, `str`, `bool`, `tuple`

## Mutations

Changing a list directly:

```py
primes = [2, 3, 5, 7]
primes.append(11)
```

Creating a new string based on an existing string (but assigning it to the same name as before):

```py
greeting = "Hello"
greeting = greeting + "!"
```