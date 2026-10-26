# 4-Bit Counter FSM with RUN/HOLD Control and 7-Segment Output

## 7-Segment Decoder: Karnaugh Maps (K-Maps)

This section documents the K-map simplification for each segment output of the common-cathode 7-segment display decoder.

### Inputs and Outputs

Let the 4-bit input be (D C B A), where (D) is the most significant bit and (A) is the least significant bit. The seven active-high outputs are (a,b,c,d,e,f,g).

### Segment Truth Table

![7-Segment Decoder Truth Table](7-Segment_Truth_Table_Plain.png)

| Hex | D | C | B | A | a | b | c | d | e | f | g |
|---:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| 0 | 0 | 0 | 0 | 0 | 1 | 1 | 1 | 1 | 1 | 1 | 0 |
| 1 | 0 | 0 | 0 | 1 | 0 | 1 | 1 | 0 | 0 | 0 | 0 |
| 2 | 0 | 0 | 1 | 0 | 1 | 1 | 0 | 1 | 1 | 0 | 1 |
| 3 | 0 | 0 | 1 | 1 | 1 | 1 | 1 | 1 | 0 | 0 | 1 |
| 4 | 0 | 1 | 0 | 0 | 0 | 1 | 1 | 0 | 0 | 1 | 1 |
| 5 | 0 | 1 | 0 | 1 | 1 | 0 | 1 | 1 | 0 | 1 | 1 |
| 6 | 0 | 1 | 1 | 0 | 1 | 0 | 1 | 1 | 1 | 1 | 1 |
| 7 | 0 | 1 | 1 | 1 | 1 | 1 | 1 | 0 | 0 | 0 | 0 |
| 8 | 1 | 0 | 0 | 0 | 1 | 1 | 1 | 1 | 1 | 1 | 1 |
| 9 | 1 | 0 | 0 | 1 | 1 | 1 | 1 | 1 | 0 | 1 | 1 |
| A | 1 | 0 | 1 | 0 | 1 | 1 | 1 | 0 | 1 | 1 | 1 |
| b | 1 | 0 | 1 | 1 | 0 | 0 | 1 | 1 | 1 | 1 | 1 |
| C | 1 | 1 | 0 | 0 | 1 | 0 | 0 | 1 | 1 | 1 | 0 |
| d | 1 | 1 | 0 | 1 | 0 | 1 | 1 | 1 | 1 | 0 | 1 |
| E | 1 | 1 | 1 | 0 | 1 | 0 | 0 | 1 | 1 | 1 | 1 |
| F | 1 | 1 | 1 | 1 | 1 | 0 | 0 | 0 | 1 | 1 | 1 |

### Minterms for Each Segment

Using the truth table above, the minterms where each active-high segment is 1 are:

- (a(D,C,B,A)=\Sigma m(0,2,3,5,6,7,8,9,10,12,14,15))
- (b(D,C,B,A)=\Sigma m(0,1,2,3,4,7,8,9,10,13))
- (c(D,C,B,A)=\Sigma m(0,1,3,4,5,6,7,8,9,10,11,13))
- (d(D,C,B,A)=\Sigma m(0,2,3,5,6,8,9,11,12,13,14))
- (e(D,C,B,A)=\Sigma m(0,2,6,8,10,11,12,13,14,15))
- (f(D,C,B,A)=\Sigma m(0,4,5,6,8,9,10,11,12,14,15))
- (g(D,C,B,A)=\Sigma m(2,3,4,5,6,8,9,10,11,13,14,15))

### Four-Variable K-Map Layout

Use Gray-code order for rows (DC = 00,01,11,10) and columns (BA = 00,01,11,10). Fill each cell with the corresponding output from the truth table for the selected segment.

| DC \ BA | 00 | 01 | 11 | 10 |
|:---:|:---:|:---:|:---:|:---:|
| 00 | m0 | m1 | m3 | m2 |
| 01 | m4 | m5 | m7 | m6 |
| 11 | m12 | m13 | m15 | m14 |
| 10 | m8 | m9 | m11 | m10 |

### K-Map Grids

The following grids use 1 and 0 entries in the Gray-code arrangement above. Read each grid as one segment's K-map.

#### Segment a

| DC \ BA | 00 | 01 | 11 | 10 |
|:---:|:---:|:---:|:---:|:---:|
| 00 | 1 | 0 | 1 | 1 |
| 01 | 0 | 1 | 1 | 1 |
| 11 | 1 | 0 | 1 | 1 |
| 10 | 1 | 1 | 0 | 1 |

#### Segment b

| DC \ BA | 00 | 01 | 11 | 10 |
|:---:|:---:|:---:|:---:|:---:|
| 00 | 1 | 1 | 1 | 1 |
| 01 | 1 | 0 | 1 | 0 |
| 11 | 0 | 1 | 0 | 0 |
| 10 | 1 | 1 | 0 | 1 |

#### Segment c

| DC \ BA | 00 | 01 | 11 | 10 |
|:---:|:---:|:---:|:---:|:---:|
| 00 | 1 | 1 | 1 | 0 |
| 01 | 1 | 1 | 1 | 1 |
| 11 | 0 | 1 | 0 | 0 |
| 10 | 1 | 1 | 1 | 1 |

#### Segment d

| DC \ BA | 00 | 01 | 11 | 10 |
|:---:|:---:|:---:|:---:|:---:|
| 00 | 1 | 0 | 1 | 1 |
| 01 | 0 | 1 | 0 | 1 |
| 11 | 1 | 1 | 0 | 1 |
| 10 | 1 | 1 | 1 | 0 |

#### Segment e

| DC \ BA | 00 | 01 | 11 | 10 |
|:---:|:---:|:---:|:---:|:---:|
| 00 | 1 | 0 | 0 | 1 |
| 01 | 0 | 0 | 0 | 1 |
| 11 | 1 | 1 | 0 | 1 |
| 10 | 1 | 0 | 1 | 1 |

#### Segment f

| DC \ BA | 00 | 01 | 11 | 10 |
|:---:|:---:|:---:|:---:|:---:|
| 00 | 1 | 0 | 0 | 0 |
| 01 | 1 | 1 | 0 | 1 |
| 11 | 1 | 0 | 1 | 1 |
| 10 | 1 | 1 | 1 | 1 |

#### Segment g

| DC \ BA | 00 | 01 | 11 | 10 |
|:---:|:---:|:---:|:---:|:---:|
| 00 | 0 | 0 | 1 | 1 |
| 01 | 1 | 1 | 0 | 1 |
| 11 | 0 | 1 | 1 | 1 |
| 10 | 1 | 1 | 1 | 1 |

### Simplified Boolean Expressions (SOP)

Using the minterms listed above and variables ordered as D (MSB), C, B, A (LSB), the minimized sum-of-products expressions are:

- **a** = BC + B\overline{D} + D\overline{A} + \overline{A}\overline{C} + AC\overline{D} + D\overline{B}\overline{C}
- **b** = \overline{A}\overline{C} + \overline{C}\overline{D} + AB\overline{D} + AD\overline{B} + \overline{A}\overline{B}\overline{D}
- **c** = A\overline{B} + A\overline{D} + C\overline{D} + D\overline{C} + \overline{B}\overline{D}
- **d** = D\overline{B} + AB\overline{C} + AC\overline{B} + BC\overline{A} + \overline{A}\overline{C}\overline{D}
- **e** = BD + CD + B\overline{A} + \overline{A}\overline{C}
- **f** = BD + C\overline{A} + D\overline{C} + \overline{A}\overline{B} + C\overline{B}\overline{D}
- **g** = AD + B\overline{A} + B\overline{C} + D\overline{C} + C\overline{B}\overline{D}

**Important:** These are SOP minimizations of the minterm lists above. The K-map grids and minterm lists must agree; use the minterm lists as the source when filling the grids.
