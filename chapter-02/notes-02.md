# Chapter 2 - Loading and Adding

### Negative Numbers

Computers represent negative numbers using two's compliment. This is a mathmatical process created by John VonNeumann for EDVAC.

2n - number ; n = number of bits in the integer

So if the number is -1 and represented in 8 bits (0x01) then:
2 to the 8th -1 = 256 - 1 = 255 = 0xFF

[Explenation Video](https://www.youtube.com/watch?v=m_G3z-C1C2g)

### Big vs. Little Endian

Represents the direction that binary value is stored.

Big Endian - Most significant to least

Little Endian - Least significant to most

Example:
```
32 Bit representation of 1

Big Endian 
01 00 00 00

Little Endian
00 00 00 01
```

Arm supports both format (bi-endian), and most arm based computers use little endian.

One advantage of little endian is that it makes it easy to change the size of integers, without requiring any address arithmetic.

NOTE: Many protocols like TCP/IP use big endian and so require tranformation when moving data.

### Shifting and Rotating

Shifting all the bits left one spot is the same as multiplying by 2(n), shifting to the right is dividing by 2(n).

When shifting and rotating it is useful to include the carry flag. Adding two 64 bit numbers that have a result larger than 64 bits results in the carry flag being set.

`Logical Shift Left` - zeros come in on the right and the bit shifted out ends up in the carry flag.

`Logical Shift Right` - zeros come in from the left, and last bit shifted out ends up in the carry flag

`Arithmetic Shfit Right` - Logical shifts cause negative numbers to turn positive. To preserve the sign use Arithmetic shifts. If the number is negative a 1 comes in from the left, if it's positive then a zero comes from the right.

`Rotate Right` - Like shift but values at the end wrap instead of being dropped. 

## Loading Registers




