# Python Lab

Lab activities for general Python programming workshop.

Attached is a [`calc.py`](./calc.py) script, which is a basic functional calculator program.

## Tasks

Whilst you can complete the tasks in any order, they start easier and get harder, so we'd recommend completing them in order. Each new feature must not break functionality introduced in a previous.

Each task is presented with an example output. This is merely an example - feel free to write it however you wish.

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

### Rather than entering numbers for each of the operations, use the mathematical symbol ("+" for addition etc)

```
Select operation:
- Add (+)
- Subtract (-)
- Multiply (*)
- Divide (/)
Enter choice: +
```

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

Bonus: Use the square symbol (`²`) for the operation and display

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
3 / 0 failed: ZeroDivisionError: float division by zero
Enter choice:
```

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
