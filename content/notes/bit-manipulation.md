---
title: "Bit Manipulation"
date: "2022-12-06"
---
In digital systems, numbers are often represented using a series of bits, where each bit is either a 0 or a 1. This is known as binary representation. For example, the number 5 could be represented as 101 in binary.

There are multiple ways to express negative numbers:
1. The **one's complement** of a binary number is simply the value you get by swapping all of the 0s for 1s and all of the 1s for 0s. For example, the one's complement of 101 (the binary representation of 5) is 010.
2. The **two's complement** (used in c++) is a little bit more complex. To find the two's complement of a binary number, you first take the one's complement of the number, as described above, and then add 1 to the result. So for our example, the two's complement of 101 would be 010 (the one's complement of 101) plus 1, which is equal to 011.
3. The **sign bit** is the most significant bit (the leftmost bit) of a number. It is used to represent the sign of a number, with a value of 0 indicating a positive number and a value of 1 indicating a negative number.

## Operators
* The **AND operator (&)** compares two bits and returns 1 if both bits are 1, and 0 otherwise.

> [!tip] Tip
> - `x & 1` is true if x is odd
> - x is divisible by $2^k$ when `x & (pow(2, k) - 1)` is false

* The **OR operator (|)** compares two bits and returns 1 if either of the bits is 1, and 0 otherwise.
* The **XOR (exclusive OR) operator (^)** compares two bits and returns 1 if either of the bits is 1, but not both. It returns 0 if both bits are 0 or both are 1.
* The **NOT operator (~)** is a unary operator that flips the bits of its operand, so that any bit that is 1 becomes 0 and vice versa.
* The **left shift operator (<<)** shifts the bits of its operand to the left by a specified number of places, filling in the empty spaces on the right with zeroes. This has the effect of multiplying the operand by a power of two.
* The **right shift operator (>>)** shifts the bits of its operand to the right by a specified number of places, filling in the empty spaces on the left with zeroes. This has the effect of dividing the operand by a power of two.

## Useful combinations
- Get bit:  `n & (1 << k)`
- Set bit to 1: `x | (1 << k)`
- Set bit to 0: `x & ~(1 << k)`
- Toggle a bit: `x ^ (1 << k)`
- LSB (Least Significant Bit): `x & 1`

## Other functions (C++)
* Zeros at beginning: `__builtin_clz(x)`
* Zeros at end: `__builtin_ctz(x)`
* Number of 1s: `__builtin_popcount(x)`
* Parity of number of 1s: `__builtin_parity(x)`

## Representing sets
To represent a set using bits, you can use a bit vector. A bit vector is a sequence of bits, where each bit represents an element in the set. For example, if the bit vector is 10110, then it represents the set {1, 3, 4}, because the first, third, and fourth bits are 1 and the second and fifth bits are 0.

Furthermore, you can use these operations
- $a \cap b$ = `a & b`
- $a \cup b$ = `a | b`
- $\overline{a}$ = `~a`
- $a \setminus b$ = `a & (~b)`

To get subsets, you can use:

```cpp
// iterate through all subsets of size n
for (int i = 0; i < (1 << n); i++) {}

// subsets of any set x
// prove (why?)
int b = 0;
do {} while (b = (b - x) & x);
```