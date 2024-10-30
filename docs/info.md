<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works

This project uses a 4x4 Array Multiplier to multiplies two four-bit numbers together, using a series of full adders to result in an 8 bit product. The multiplier works by systematically multiplying each bit of the first number with each bit of the second number. These partial products are then combined using a series of full adders to form the final result.
```mermaid
graph TB
  %% Inputs
  A(A3, A2, A1, A0) --> P00(AND A3*B0)
  A --> P01(AND A2*B0)
  A --> P02(AND A1*B0)
  A --> P03(AND A0*B0)

  A --> P10(AND A3*B1)
  A --> P11(AND A2*B1)
  A --> P12(AND A1*B1)
  A --> P13(AND A0*B1)

  A --> P20(AND A3*B2)
  A --> P21(AND A2*B2)
  A --> P22(AND A1*B2)
  A --> P23(AND A0*B2)

  A --> P30(AND A3*B3)
  A --> P31(AND A2*B3)
  A --> P32(AND A1*B3)
  A --> P33(AND A0*B3)

  %% Full Adders
  P00 --> FA00(Full Adder)
  P10 --> FA01
  P01 --> FA02
  P11 --> FA03
  FA00 --> Sum0(Sum 0)

  P02 --> FA10(Full Adder)
  P12 --> FA11
  P03 --> FA12
  P13 --> FA13
  FA10 --> Sum1(Sum 1)

  P20 --> FA20(Full Adder)
  P30 --> FA21
  P21 --> FA22
  P31 --> FA23
  FA20 --> Sum2(Sum 2)

  P22 --> FA30(Full Adder)
  P32 --> FA31
  P23 --> FA32
  P33 --> FA33
  FA30 --> Sum3(Sum 3)

  %% Output connections
  Sum0 --> P0(Product Bit 0)
  Sum1 --> P1(Product Bit 1)
  Sum2 --> P2(Product Bit 2)
  Sum3 --> P3(Product Bit 3)
  FA00 --> Carry0(Carry 0)
  FA10 --> Carry1(Carry 1)
  FA20 --> Carry2(Carry 2)
  FA30 --> Carry3(Carry 3)
  Carry0 --> P4(Product Bit 4)
  Carry1 --> P5(Product Bit 5)
  Carry2 --> P6(Product Bit 6)
  Carry3 --> P7(Product Bit 7)


```


## How to test

Input two 4-bit binary numbers and manually verify the output.
For example:
1st num: 1001
2nd num: 1011
Output: 1100011 (binary), or 0x63 (hexadecimal)
The format of the output can be adjusted in test.py, but the value they represent should be accurate to the product of the two 4-bit binary numbers.
## External hardware
N/A
