- exhaustive enumeration is a 'guess and check' method for implementing an algorithm. You throw in some guesses for a problem until you find a solution, and if all possibilities are exhausted, no solution is found.
-  "We
enumerate all possibilities until we get to the right answer or exhaust
the space of possibilities"
- "The trick of
initializing a variable before entering a loop, and then checking
whether that value has been changed upon exit, is a common one."
- Computers deal with the numbers we insert to it in the binary number system (0,1)
- The Computer converts decimal numbers to binary numbers in order to deal with it, dealing with decimal integers is easier than decimal floats
- [Conversions from binary to decimal through multiplying by 2](https://www.tutorialspoint.com/digital-electronics/binary-to-decimal-conversion.htm)
- [Conversions from decimal to binary through double dabble / division](https://www.tutorialspoint.com/digital-electronics/decimal-to-binary-conversion.htm)
- floats have a precision of 53 bits in python.
- floats that have an infinite precision are approximated, floats that have a finite precision are kept as they are.
- RAM represents floating points as ``(significant binary, exponent)``
- Example of infinite precision: ``0.1`` and it cannot be represented in the sig and exp order.
- Example of finite precision: ``0.125`` or ``0.625`` and they can be represented in the sig and exp order.
- The "sig and exp" basically means what is the ``sig`` multiplied by two to the power of ``exp`` to give the requested float

```
What about the decimal fraction 1/10, which we write in Python
as 0.1? The best we can do with four significant binary digits is
(0011, -101). This is equivalent to 3/32, i.e., 0.09375. If we had five
significant binary digits, we would represent 0.1 as (11001, -1000),
which is equivalent to 25/256, i.e., 0.09765625. How many significant
digits would we need to get an exact floating-point representation of
0.1? An infinite number of digits! There do not exist integers sig and
exp such that sig * 2-exp equals 0.1. So, no matter how many bits
Python (or any other language) uses to represent floating-point
numbers, it can represent only an approximation to 0.1. In most
Python implementations, there are 53 bits of precision available for
floating-point numbers, so the significant digits stored for the
decimal number 0.1 will be
11001100110011001100110011001100110011001100110011001
This is equivalent to the decimal number
0.1000000000000000055511151231257827021181583404541015625
```
