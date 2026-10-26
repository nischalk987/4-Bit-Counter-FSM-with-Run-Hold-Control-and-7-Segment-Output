# 4-Bit Counter FSM with RUN/HOLD Control and 7-Segment Output

## 7-Segment Decoder: Karnaugh Maps (K-Maps)

This section documents the K-map simplification for each segment output of the common-cathode 7-segment display decoder.

### Inputs and Outputs

Let the 4-bit input be (D C B A), where (D) is the most significant bit and (A) is the least significant bit. The seven active-high outputs are (a,b,c,d,e,f,g).

### Segment Truth Table

![7-Segment Decoder Truth Table](7-Segment_Truth_Table_Plain.png)

### K-Map Grids

The following grids use 1 and 0 entries in the Gray-code arrangement above. Read each grid as one segment's K-map.

#### Segment a

![Segment a K-map, minterms, and minimized SOP](Segment_a_Plain1.png)

#### Segment b

![Segment b K-map, minterms, and minimized SOP](Segment_b_Plain.png)

#### Segment c

![Segment c K-map, minterms, and minimized SOP](Segment_c_Plain.png)

#### Segment d

![Segment d K-map, minterms, and minimized SOP](Segment_d_Plain.png)

#### Segment e

![Segment e K-map, minterms, and minimized SOP](Segment_e_Plain.png)

#### Segment f

![Segment f K-map, minterms, and minimized SOP](Segment_f_Plain.png)

#### Segment g

![Segment g K-map, minterms, and minimized SOP](Segment_g_Plain.png)
