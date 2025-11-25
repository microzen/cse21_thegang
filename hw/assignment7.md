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

### Question 4

An composition of a non-negative integer n into k parts is a k-tuple of non-negative integers that sum
up to n. For example, (2, 0, 1, 3, 0, 4) and (0, 0, 10, 0, 0, 0) are both compositions of 10 into 6 parts.

a) What is the minimum number of bits necessary to uniquely encode each compositions of 10 into
6 parts?

**Solution**:

Number of ways to encode each composition of 10 into 6 parts: $\dbinom{10 + 6 -1}{6 - 1} = \dbinom{15}{5}$

Number of bits necessary to uniquely code each compositions of 10 into 6 parts:
$$\displaystyle\log_2\dbinom{15}{5} \approx 12 \text{ bits} $$


b) Develop an encoding strategy and encode (2, 0, 1, 3, 0, 4) and (0, 0, 10, 0, 0, 0) using the number of bits calculated from the previous part.

**Solution**:

We use Stars and Bars method. We convert the compositions of 10 into 6 parts into fixed length 15 bits binary strings, each of which uses 5 "1"s to separate 6 parts and "0"s to represent the number of units that part has. So, (2,0,1,3,0,4) can be converted to 001101000110000.

 We then put them in a dictionary of Rank 15 choose 5 using lexicographical order. Now, there are a total of $\dbinom{15}{5} = 3003$ compositions. Hence, we only need a 12 bit binary string with 5 "1"s to encode the decimal position number of each composition.

 We do that by write the numbers n-1 down to 0 under each bit of the 15 bit string from left to right.  Then, we write the numbers k down to 1 under each "1" from left to right. For each "1", we add the first number "chose" the second number. If first number is smaller than the second number, the combination is 0.

 This is the shortcut of the ranking algorithm for Rank 15 Choose 5.

 Using this method, (2,0,1,3,0,4) is encoded as $\dbinom{12}{5}+\dbinom{11}{4}+\dbinom{9}{3}+\dbinom{5}{2}+\dbinom{4}{1} = 1220$ in decimal and 010001110011 in binary, while {0,0,10,0,0,0} is encoded as $\dbinom{14}{5}+\dbinom{13}{4}+\dbinom{2}{3}+\dbinom{1}{2}+\dbinom{0}{1} = 2717$ in decimal and 1010 1001 1101 in binary.

c) Use your encoding strategy to decode the following string:
$$0011 1010 1100$$

Solution:

To decode a string representing the position of a n = 15-bit string with k = 5 "1"s, we initialize output to be a 15-bit string of "0"s. Let r that position string in decimal. While k > 0, we find the largest x such that $\dbinom{x}{k}\le r$, then put a 1 in position x (counting from the right), then substract $\dbinom{x}{k}$ from r and substract 1 from k. Using this method, the string $001110101100_2 = 940_{10}$ will start with r = 940, n = 15, and k = 5. After decoding, we find out that the string represents the number 001001001000110. We treat the "1"s as bars and the "0"s as stars, and we can decode to the composition of {2,2,2,3,0,1}

Final answer: {2,2,2,3,0,1}