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
  %% Layer 1: Partial Product Generation using AND Gates
  Q0M0[AND Q0 M0] --> P0
  Q0M1[AND Q0 M1] --> FA01
  Q0M2[AND Q0 M2] --> FA02
  Q0M3[AND Q0 M3] --> FA03

  Q1M0[AND Q1 M0] --> FA01
  Q1M1[AND Q1 M1] --> FA02
  Q1M2[AND Q1 M2] --> FA03
  Q1M3[AND Q1 M3] --> FA04
  0 --> FA01 --> FA02 --> FA03 --> FA04

  Q2M0[AND Q2 M0] --> FA05
  Q2M1[AND Q2 M1] --> FA06
  Q2M2[AND Q2 M2] --> FA07
  Q2M3[AND Q2 M3] --> FA08 

  

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
