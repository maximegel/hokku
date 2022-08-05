# Built-in Types

## Scalar Types

A _scalar_ type represents a single value.

### Integer Types

An _integer_ or a whole number is a number without fractions.

| Type    | Range                                                   | Size    |
| ------- | ------------------------------------------------------- | ------- |
| `byte`  | -128 to 127                                             | 1 byte  |
| `short` | -32,768 to 32,767                                       | 2 bytes |
| `int`   | -2,147,483,648 to 2,147,483,647                         | 4 bytes |
| `long`  | -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 | 8 bytes |

Integer literals can be written in any of those forms:

```txt
decimal = 98_222
hex = 0xff
octal = 0o77
binary = 0b1111_0000
```

### Floating-Point Types

A _floating-point_ is a number with decimal point.

| Type     | Approximate range               | Precision     | Size    |
| -------- | ------------------------------- | ------------- | ------- |
| `float`  | ±1.5 x 10^−45 to ±3.4 x 10^38   | ~6-9 digits   | 4 bytes |
| `double` | ±5.0 × 10^−324 to ±1.7 × 10^308 | ~15-17 digits | 8 bytes |

Floating-point literals can be declared as follows:

```txt
two = 2.0 # doubles are implicit
six_point_four: float = 6.4 # floats are explicit
```

### The Boolean Type

A _boolean_ has two possible values: `true` and `false`. Booleans are one byte
in size.

The boolean type is specified using `bool`:

```txt
yes: bool = true
no = false # with implicit typing
```

### The Character Type

A _character_ is a single letter, surrounded by `'`. Characters are two bytes in
size.

The character type is specified using `char`:

```txt
a: char = 'a'
z = 'Z' # with implicit typing
heart_eyed_cat = '😻'
```

## Compound Types

_Compound types_ can group multiple values into one type.

### The Array Type

TODO

### The String Type

A _string_ represents an sequence of letters/characters, surrounded by `"` or
`` ` ``. In fact, a string is a glorified array of `char`.

The string type is specified using `str`:

```txt
good_moring: str = "Good morning"
good_afternoon: "Good afternoon" # with implicit typing
```

Strings can be interpolated using the `${}` syntax:

```txt
name = "Mark"
age = 34
happy_birthday = `Happy birthday, "${name}"!`
age_today = "You are ${age + 1} years old today."
```

Characters such as `"`, `` ` `` and `\` can be escaped with a `\` prefix:

```txt
he_said = `He said, "What?"`
quotes = "\"Quotes\" of `various` 'types'"
filename = "c:\\documents\\files\\notes.txt"
```

Strings can have multiple lines:

```txt
plain = `
    Some lines of text,
    with "quotes" of various 'types',
`

## Result:
    Some lines of text,
    with "quotes" of various 'types',
##
```

Use the `|` (literal) operator to strip the leading indentation and keep
newlines as they are:

```txt
litteral = | `
    Several lines of text,
    with "quotes" of various 'types',
    and a blank line:

    and some text with
        extra indentation.
`

## Result:
Several lines of text,\n
with "quotes" of various 'types',\n
and also a blank line:\n
\n
and some text with\n
    extra indentation\n
##
```

Instead, to also strip the leading indentation, but replace single newlines by
spaces; use the `>` (fold) operator:

```txt
folded = > `
    Several lines of text,
    with "quotes" of various 'types',
    and a blank line:

    and some text with
        extra indentation.
`

## Result:
Several lines of text, with "quotes" of various 'types', and a blank line:\n
and some text with\n
    extra indentation.\n
##
```

Use the `-` (strip) operator to remove leading and trailing whitespaces:

```txt
striped = - "   Text surrounded by whitespaces.
   "

## Result:
Text surrounded by whitespaces.
##
```

### The Tuple Type

A _tuple_ is a general way of grouping together a number of values with a
variety of types. Tuples have a fixed length: once declared, they cannot grow
or shrink in size.

The tuple type is specified using a comma-separated list of types surrounded by
`[]`:

```txt
steve: [int, str, bool] = [1, "Steve", true]
alice = [2, "Alice", false] # with implicit typing
```

Tuple elements can be accessed using index, the same way as an array. An index
starts from zero. For example:

```txt
numbers = [500, 6.4, 1]
five_hundred = numbers[0]
six_point_four = numbers[1]
one = numbers[2]
```
