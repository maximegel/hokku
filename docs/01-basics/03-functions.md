# Functions

```txt
hello() =
    print("Hello my friend")
    ask_name()

ask_name() = print("What is your name?")

hello()

## Result:
Hello my friend
What is your name?
##
```

When defining a parameterless function, parentheses can be avoided:

```txt
hello = print("Hello my friend")
hello()

## Result:
Hello my friend
##
```

When calling a function, parentheses can be avoided too:

```txt
hello = print "Hello my friend"
hello

## Result:
Hello my friend
##
```

## Parameters

```txt
hello_alan = hello "Alan"
hello(name: str) = print "Hello ${name}"

hello_alan

## Result:
Hello Alan
##
```

When defining multiple parameters, separate the parameter declarations with `,`:

```txt
print_measurement(value: int, unit: char) =
    print "The measurement is: ${value}${unit}"

print_measurement 5, 'm'

## Result:
The measurement is: 5m
##
```

## Linear Body

Function bodies are made up exclusively of functions calls (aka. expressions).
There can only be one expression per line. Each expression take the result of
the previous expression as input and pass its output to the next expression and
so on:

```txt
sum(x: int, y: int, z: int) =
    x
    add y
    add z

print "The sum is: ${sum 6, 2, 7}"

## Result:
The sum is: 15
##
```

## Lambdas

A _lambda_ function is a small anonymous function. A lambda function can take
any number of arguments, but can only have one expression. The syntax of a
lambda is the same as a function, but without name.

```txt
print_multiple(x: int, multiplier: (n: int) -> int) =
    print "The multiple of ${x} is: ${multiplier x}"

print_multiple 11, (n) = n * 2

## Result:
The multiple of 11 is: 22
##
```

The power of lambdas is also shown when used as an anonymous function inside
another function. For example, by defining a function which returns a lambda,
the result can be use to create more specific functions:

```txt
multiplier(n: int) =
    (x) = x * n

doubler = multiplier 2
tripler = multiplier 3

print "The double of 11 is: ${doubler 11}"
print "The triple of 11 is: ${tripler 11}"

## Result:
The double of 11 is: 22
The triple of 11 is: 33
##
```
