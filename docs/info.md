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
  A0B0[AND A0 B0] --> S00
  A0B1[AND A0 B1] --> FA01
  A0B2[AND A0 B2] --> FA02
  A0B3[AND A0 B3] --> FA03

  A1B0[AND A1 B0] --> FA10
  A1B1[AND A1 B1] --> FA11
  A1B2[AND A1 B2] --> FA12
  A1B3[AND A1 B3] --> FA13

  A2B0[AND A2 B0] --> FA20
  A2B1[AND A2 B1] --> FA21
  A2B2[AND A2 B2] --> FA22
  A2B3[AND A2 B3] --> FA23

  A3B0[AND A3 B0] --> FA30
  A3B1[AND A3 B1] --> FA31
  A3B2[AND A3 B2] --> FA32
  A3B3[AND A3 B3] --> FA33

  %% Layer 2: First Row of Additions
  S00 --> FA10
  FA01 --> FA11
  FA02 --> FA12
  FA03 --> FA13

  %% Layer 3: Second Row of Additions
  FA10 --> FA20
  FA11 --> FA21
  FA12 --> FA22
  FA13 --> FA23

  %% Layer 4: Third Row of Additions
  FA20 --> FA30
  FA21 --> FA31
  FA22 --> FA32
  FA23 --> FA33

  %% Output Connections
  FA33 --> Result

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
