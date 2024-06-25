For Toggling Bits
Suppose num is initially 0 (which is 0000 0000 in binary) and we are working with the 2nd bit position (k = 2).

Setting a Bit (SETBIT)
c
Copy code
num = SETBIT(num, 2);
Binary before: 0000 0000
Operation: 0000 0000 | 0000 0100 (1 << 2)
Binary after: 0000 0100 (4 in decimal)
Clearing a Bit (CLEARBIT)
c
Copy code
num = CLEARBIT(num, 2);
Binary before: 0000 0100
Operation: 0000 0100 & 1111 1011 (~(1 << 2))
Binary after: 0000 0000 (0 in decimal)
Toggling a Bit (TOGGLEBIT)
c
Copy code
num = TOGGLEBIT(num, 2);
Binary before: 0000 0000
Operation: 0000 0000 ^ 0000 0100 (1 << 2)
Binary after: 0000 0100 (4 in decimal)
If you toggle the bit again:

c
Copy code
num = TOGGLEBIT(num, 2);
Binary before: 0000 0100
Operation: 0000 0100 ^ 0000 0100 (1 << 2)
Binary after: 0000 0000 (0 in decimal)

Too SWAP NIBBLE
Explanation
Extract the lower nibble: x & 0x0F

0x0F in binary is 00001111.
This operation masks out the upper 4 bits, leaving only the lower 4 bits.
Extract the upper nibble: x & 0xF0

0xF0 in binary is 11110000.
This operation masks out the lower 4 bits, leaving only the upper 4 bits.
Shift the lower nibble to the upper position: (x & 0x0F) << 4

This shifts the lower 4 bits to the left by 4 positions.
Shift the upper nibble to the lower position: (x & 0xF0) >> 4

This shifts the upper 4 bits to the right by 4 positions.
Combine the shifted nibbles: ((x & 0x0F) << 4) | ((x & 0xF0) >> 4)

This combines the two shifted nibbles to form the byte with swapped nibbles.






