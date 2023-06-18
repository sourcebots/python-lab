# Python Lab

Lab activities for general Python programming workshop.

Attached is a [`calc.py`](./calc.py) script, which is a basic functional calculator program.

## Tasks

Whilst you can complete the tasks in any order, they start easier and get harder, so we'd recommend completing them in order.

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
- Exponent (^)
Enter choice: ^
Enter first number: 2
Enter second number: 3
2 ** 3 = 5
```

In Python, the "power of" operator is `**`, but to keep the operations a single character, use "^".

### Implement squaring, where only a single number is prompted

```
Select operation:
- Add (+)
- Subtract (-)
- Multiply (*)
- Divide (/)
- Exponent (^)
- Square (2)
Enter choice: 2
Enter first number: 3
3 ** 2 = 9
```

### Ask for all inputs at once, much like a conventional calculator

```
Available operations:
- Add (+)
- Subtract (-)
- Multiply (*)
- Divide (/)
- Exponent (^)
- Square (**)

> 2 + 3
= 5
```

### Support "prefix" notation, where the operator comes before the numbers

```
Available operations:
- Add (+)
- Subtract (-)
- Multiply (*)
- Divide (/)
- Exponent (^)
- Square (**)

> + 2 3
= 5
```
