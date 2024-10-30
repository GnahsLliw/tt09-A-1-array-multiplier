<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works

This project uses a 4x4 Array Multiplier to multiplies two four-bit numbers together, using a series of full adders to result in an 8 bit product. The multiplier works by systematically multiplying each bit of the first number with each bit of the second number. These partial products are then combined using a series of full adders to form the final result.
```mermaid
graph TD
  %% Inputs
  A(A0,A1,A2,A3) --> P00(P0,0)
  A(A0,A1,A2,A3) --> P01(P0,1)
  A(A0,A1,A2,A3) --> P02(P0,2)
  A(A0,A1,A2,A3) --> P03(P0,3)

  B(B0,B1,B2,B3) --> P10(P1,0)
  B(B0,B1,B2,B3) --> P11(P1,1)
  B(B0,B1,B2,B3) --> P12(P1,2)
  B(B0,B1,B2,B3) --> P13(P1,3)

  %% Partial Products
  P00 --> FA0(Full Adder)
  P10 --> FA0
  FA0 --> Sum0(Sum 0)
  FA0 --> Carry0(Carry 0)
  
  P01 --> FA1(Full Adder)
  P11 --> FA1
  FA1 --> Sum1(Sum 1)
  FA1 --> Carry1(Carry 1)
  
  P02 --> FA2(Full Adder)
  P12 --> FA2
  FA2 --> Sum2(Sum 2)
  FA2 --> Carry2(Carry 2)
  
  P03 --> FA3(Full Adder)
  P13 --> FA3
  FA3 --> Sum3(Sum 3)
  FA3 --> Carry3(Carry 3)

  %% Outputs
  Sum0 --> Product0(Product Bit 0)
  Sum1 --> Product1(Product Bit 1)
  Sum2 --> Product2(Product Bit 2)
  Sum3 --> Product3(Product Bit 3)
  Carry0 --> Product4(Product Bit 4)
  Carry1 --> Product5(Product Bit 5)
  Carry2 --> Product6(Product Bit 6)
  Carry3 --> Product7(Product Bit 7)

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
