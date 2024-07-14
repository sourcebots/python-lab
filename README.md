# Python Lab

Lab activities for general Python programming workshop.

Attached is a [`calc.py`](./calc.py) script, which is a basic functional calculator program.

## Tasks

Whilst you can complete the tasks in any order, they start easier and get harder, so we'd recommend completing them in order. Each new feature must not break functionality introduced in a previous.

Each task is presented with an example output. This is merely an example - feel free to write it however you wish.

### List the operations again after each calculation

```
Select operation.
1.Add
2.Subtract
3.Multiply
4.Divide
Enter choice(1/2/3/4): 1
Enter first number: 1
Enter second number: 1
1 + 1 = 2
Let's do next calculation? (yes/no): yes

Select operation.
1.Add
2.Subtract
3.Multiply
4.Divide
Enter choice(1/2/3/4):
```

<details>

<summary>Hint</summary>

`while True` means "run this code forever". This is what keeps re-running our code over and over again.

Python uses indenting to identify when blocks of code start or end. The `while` loop acts on everything indented 1 level further in than it.

If the user doesn't want to do another calculation, `break` will "break" out of the loop, stop running the code in the loop, and run the rest of the program.

</details>

### Show a message when the user enters an invalid operation

```
Select operation.
1.Add
2.Subtract
3.Multiply
4.Divide
Enter choice(1/2/3/4): 5
Invalid choice - try again
Enter choice(1/2/3/4): 5
```

<details>

<summary>Hint</summary>

The `else` statement can be used to run code when the `if` (or related `elif`) blocks aren't executed:

```python
x = 4
if x > 5:
    print("x is greater than 5")
else:
    print("x is less than or equal to 5")
```

Also, you can use the `continue` statement to return to the top of the `while` loop, and execute it again.

</details>

### Rather than entering numbers for each of the operations, use the mathematical symbol ("+" for addition etc)

```
Select operation:
- Add (+)
- Subtract (-)
- Multiply (*)
- Divide (/)
Enter choice: +
```

<details>

<summary>Hint</summary>

The choices are currently numbers (`if choice == "1"`).

Reusing the `choice` in the `print` statement, or the calculation itself, might reduce duplication - but it might be at the cost of readability.

</details>

### Add support for operating on decimal values

```
Select operation:
- Add (+)
- Subtract (-)
- Multiply (*)
- Divide (/)
Enter choice: +
Enter first number: 2.5
Enter second number: 3.5
2.5 + 3.5 = 6
```

<details>

<summary>Hint</summary>

Python has 2 main numeric types. An `int` represents a whole number, whilst a `float` _can_ also include a fractional component (but don't have to).

```python
>>> type(1)
<class 'int'>
>>> type(1.5)
<class 'float'>
>>> type(1.0)
<class 'float'>
```

Where in the code is the user's input converted to an `int`?

</details>

### When prompted for a number, if someone enters something which isn't a number, show an error message and ask for the value again

```
Select operation:
- Add (+)
- Subtract (-)
- Multiply (*)
- Divide (/)
Enter choice: +
Enter first number: no
"no" is not a number. Try again.
Enter first number: no
```

<details>

<summary>Hint</summary>

Sometimes, it's easier to ask for forgiveness than permission. Rather than trying to check whether something is a number, try doing something with it, and complain if it goes wrong.

```python
try:
    num = int("no")
except ValueError:
    print("'no' is not a number.")
```

`int` (and `float`) _raises_ a `ValueError` if it receives a string it can't convert. `try` and `except` allow us to _catch_ this _exception_ and do something about it, without our code crashing.

</details>

Extension: If someone gives an invalid value for the second number, don't ask for the first number again.

### Add a "Power of" choice, which raises the first number to the power of the second.

```
Select operation:
- Add (+)
- Subtract (-)
- Multiply (*)
- Divide (/)
- Exponent (**)
Enter choice: **
Enter first number: 2
Enter second number: 3
2 ** 3 = 8
```

In Python, the "power of" operator is `**`.

### Implement square root, where only a single number is prompted

```
Select operation:
- Add (+)
- Subtract (-)
- Multiply (*)
- Divide (/)
- Exponent (**)
- Square Root (sqrt)
Enter choice: sqrt
Enter first number: 9
sqrt 9 = 3
```

<details>

<summary>Hint</summary>

We know which choice the user wants (`choice`) before we prompt them for each number. Maybe the second number (`num2`) is only asked for when the choice uses it?

</details>

### If the calculation fails, show a sensible message

```
Select operation:
- Add (+)
- Subtract (-)
- Multiply (*)
- Divide (/)
- Exponent (**)
- Square Root (sqrt)
Enter choice: /
Enter first number: 3
Enter second number: 0
3 / 0 failed: ZeroDivisionError: division by zero
Enter choice:
```

<details>

<summary>Hint</summary>

Exceptions have a type and a message. To get the exception as a variable, use `as`:

```python
try:
    divide(1, 0)
except Exception as e:
    print(type(e))  # "ZeroDivisionError"
    print(str(e))  # "division by zero"
```

You can also handle specific exceptions. `Exception` can be used to handle all exceptions.

```python
try:
    divide(1, 0)
except ZeroDivisionError:
    print("You can't divide by zero!")
except ValueError as e:
    print("Were both arguments numbers?")
except Exception as e:
    print("Something else happened!")
    print(type(e))
    print(str(e))
```

</details>


### Let the user enter the entire equation at once

```
Available operations:
- Add (+)
- Subtract (-)
- Multiply (*)
- Divide (/)
- Exponent (**)
- Square (sqrt)

> 2 + 3
= 5
```


<details>

<summary>Hint</summary>

You can split a string by using the `split` method:

```python3
>>> "2 + 3".split(" ")
["2", "+", "3"]
```

This gives you a list, and you can retrieve specific values from using `[0]` (the first entry in a list is at position 0):

```python3
>>> args = "2 + 3".split(" ")
>>> args[1]
"+"
```

</details>

### Support "[Reverse Polish](https://www-stone.ch.cam.ac.uk/documentation/rrf/rpn.html)" notation, where the operator comes after the numbers

```
Available operations:
- Add (+)
- Subtract (-)
- Multiply (*)
- Divide (/)
- Exponent (**)
- Square (sqrt)

> 2 3 +
= 5
```

This should work in addition to normal (infix) notation.

<details>

<summary>Hint</summary>

Try finding where the operator is in the equation:

```python3
>>> args = "2 + 3".split(" ")
>>> try:
...     int(args[2])
... except ValueError:
...     print("The last item isn't a number")
```

If you try and retrieve an item which doesn't exist, you'll receive an `IndexError`:

```python3
>>> args[4]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list index out of range
```

</details>
