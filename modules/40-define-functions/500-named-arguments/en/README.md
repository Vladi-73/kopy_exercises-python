
In this lesson, we'll look at what parameters exist, how they differ, and when to apply them.

**Arguments** are data that are passed to a function call. They come in two types:

The first type is **positional arguments**. They are passed in the same order as the function parameters are defined:

```python
# (text, length)
truncate('My Text', 3)
```

The second type is **named arguments**. They are passed not just as values, but as a pair "name=value". So you can pass them in any order:

```python
# Arguments are passed in a different order
truncate(length=3, text='My Text')
```

If you look carefully at the two examples above, you can see that they are two identical functions.

Now let's see when to apply these types of arguments.

The type of parameter you choose depends on who is calling the function.

There are two reasons to use named arguments:

* They increase readability because you can see the names at a glance

* You can leave out all the intermediate parameters that we don't need right now

The latter is useful if the function has many optional parameters. Let's look at an example:

```python
def print_params(a=1, b=2, c=3, d=4):
    print(a, b, c, d)

# You only need to pass d, but you have to pass all
f(1, 2, 3, 8)

# Named arguments allow you to pass only d
# Default values are used for the other arguments
f(d=8)
```

Named arguments can be passed at the same time as positional arguments. Then positional arguments must go at the beginning:

```python
# Transmit only a (positional) and d (as named)
f(3, d=3)
```
