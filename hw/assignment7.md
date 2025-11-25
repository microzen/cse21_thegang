# Assignment 7

Contributors:
- Yezhi Wu, yew020@ucsd.edu
- Andrew Le, aal034@ucsd.edu
- Theo Lee, thl030@ucsd.edu
- Woosik Kim, wok017@ucsd.edu

Due: November 25 2025

---

### Question 2
In classic 8-bit games like Super Mario Bros., character sprites are made up of small pixel images. The Bullet Bill sprite is 16 pixels wide and 16 pixels tall and is black and white.

Each color can be represented by 1 bit: 0 = white 1 = black

**a).** How many bits are required to encode this image by encoding each pixel with 2 bits?

$$16 \text{ pixels } \times 16 \text{ pixels } \times 2 = 2$$

**b).** Huffman encoding is sometimes used in image compression.

We can use hexadecimal to encode each of the squares into a single hexadecimal character: { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F }

The hexadecimal characters for this image are:
Then we compute the frequency table of the hexadecimal characters and build a Huffman code based on that. Then encode the hexadecimal string using the Huffman code.

Here is the frequency table for this particular image (there are a total of 64 hexadecimal characters that make up the image.):

|Character|0|1|2|3|4|5|6|7|8|9|A|B|C|D|E|F|
|---------|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|Frequency|12|1|0|8|0|3|0|2|2|1|1|1|6|1|4|22|

**i.** Draw the huffman tree for the set of frequencies.

![/huffman_as7.png](./huffman_as7.png)

**ii.** Give the code for each character.
- 0: 11
- 1: 010001
- 2: 10001110
- 3: 011
- 4: 100011110
- 5: 1001
- 6: 10001111
- 7: 01001
- 8: 10000
- 9: 0100000
- A: 0100001
- B: 100010
- C: 101
- D: 11
- E: 0101
- F: 00

**iii.** Calculate the total number of bits needed to encode this particular image of Bullet Bill using the coding.

|Character|Frequency|Code Length|Total Bits|
|-|-|-|-|
|F|22|2|44|
|0|12|2|24|
|3|8|3|24|
|C|6|3|18|
|E|4|4|16|
|5|3|5|15|
|7|2|5|10|
|8|2|5|10|
|1|1|6|6|
|9|1|6|6|
|A|1|6|6|
|B|1|6|6|
|D|1|6|6|
|2|0|8|0|
|4|0|8|0|
|6|0|7|0|

Therefore, $44+24+24+18+16+15+10+10+6+6+6+6+6+0+0+0=191$