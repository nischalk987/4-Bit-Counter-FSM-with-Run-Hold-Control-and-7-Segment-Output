# 4-Bit Counter FSM with RUN/HOLD Control and 7-Segment Output

## 7-Segment Decoder: Karnaugh Maps (K-Maps)

This section documents the K-map simplification for each segment output of the common-cathode 7-segment display decoder.

### Inputs and Outputs

Let the 4-bit input be (D C B A), where (D) is the most significant bit and (A) is the least significant bit. The seven active-high outputs are (a,b,c,d,e,f,g).

### Segment Truth Table

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

### Simplified Boolean Expressions

These expressions are to be validated against the truth table and the grouping choices in the K-maps before using them in the decoder implementation.

- (a = D + B + AC + \overline{A}\,\overline{C} + \overline{B}\,\overline{C}\)
- (b = \overline{C} + \overline{A}\,\overline{B} + AB + \overline{D}C)
- (c = A + C + \overline{B})
- (d = B\overline{C} + A\overline{C} + \overline{A}B + \overline{B}C + \overline{D}\,\overline{A}\)
- (e = \overline{A}\,\overline{C} + B\overline{C} + D\overline{B} + \overline{A}D + \overline{B}\,\overline{C})
- (f = D + \overline{A}\,\overline{B} + C\overline{A} + C\overline{B} + \overline{C}\,\overline{B})
- (g = D + A\overline{B} + B\overline{A} + C\overline{A} + C\overline{B})

> **Note:** The Boolean expressions above should be checked by deriving them from the displayed K-map grids. Do not treat them as verified minimum expressions until validated.

