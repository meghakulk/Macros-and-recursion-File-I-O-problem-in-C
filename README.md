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
