# Assignment 7

Contributors:
- Yezhi Wu, yew020@ucsd.edu
- Andrew Le, aal034@ucsd.edu
- Theo Lee, thl030@ucsd.edu
- Woosik Kim, wok017@ucsd.edu

Due: November  25 2025

---

### Question 1

You own an pizza shop. You wish to encode each order with a fixed length binary string ( in order to efficiently store the orders in your computer.)

A single order consists of a size, a type of crust, a type of sauce, and toppings.

You can choose a size : small, medium, large

The crust choices are : thin, thick, stuffed, gluten-free

The sauce choices ae : tomato, pesto

Then there are toppings that you have the option to select or not. The toppings are : pepperoni, olives, mushrooms, sausage, eggplant. ( You can select any number of the toppings including selecting 0 toppings.)

**a)** How many bits does it require to encode each order with the fewest bits using a fixed-length encoding ?

Solution :

* Size : small, medium, large $\rightarrow$ 3 choices.

Smallest k with $2^k$ $\ge$ 3 is k = 2. $\rightarrow$ need 2 bits.

* Crust : thin, thick, stuffed, gluten-free $\rightarrow$ 4 choices.

$2^2$ = 4 $\rightarrow$ need 2 bits.

* Sauce : tomato, pesto $\rightarrow$ 2choices.

$2^1$ = 2 $\rightarrow$ need 1 bit.

* Toppings : 5 toppings, each can be on or off. So number of combinations = $2^5$ = 32.

$2^5$ = 32 $\rightarrow$ needs 5 bits.

Total bits for one full order : \
2(size) + 2(crust) + 1(sauce) + 5(toppings) = 10bits

Total distinct order = 3 * 4 * 2 * 32 = 768

We need at least [$log_2 768$] = 10 bits for a fixed-length code.

**Answer (a)** : 10 bits.

**b)** Develop your own encoding/decoding algorithm where the code uses this number of bits. (Please
give a brief description of how it works on an particular order.)

* Encoding algorithm :
1. The first 2 bits represent the size.
2. The next 2 bits represent the crust.
3. The next 1 bit represents the sauce.
4. The last 5 bits represent toppings in the order: pepperoni, olives, mushrooms, sausage, eggplant
(1 = included, 0 = not included). \
To encode an order, I look up each category’s bit value and concatenate all 10 bits into one binary string.

* Decoding algorithm :
1. Bits 1-2 $\rightarrow$ size
2. Bits 3-4 $\rightarrow$ crust
3. Bit 5 $\rightarrow$ sauce
4. Bits 6-10 $\rightarrow$ toppings\
I translate each bit section back into its meaning using the tables from the encoding step. \
 If the size bits equal 11 (an unused combination), I mark the code as “not decodable.”

 **c)** Use your encoding to encode the following orders : 

### Size ( 2 bits )
- 00 = small
- 01 = medium
- 10 = large
- 11 = should not use this

### Crust ( 2 bits )
- 00 = thin
- 01 = thick
- 10 = stuffed
- 11 = gluten-free

### Sauce ( 1 bit )
- 0 = tomato
- 1 = pesto

### Toppings ( 5 bits )
1. pepperoni
2. olives
3. mushrooms
4. sausage
5. eggplant

For each topping :
* 1 = topping is included
* 0 = topping is not included
--- 
* size : small ( 00 )
* crust : gluten - free ( 11 )
* sauce : pesto ( 1 )
* toppings : eggplant ( 00001 )

Binary string : 0011100001

* size : large ( 10 )
* crust : thin ( 00 )
* sauce : tomato ( 0 )
* toppings : pepperoni, olives, sausage, eggplant ( 11011 )

Binary string : 1000011011

**d)** Use your decoding to decode the following strings: (put “not decodable” if you can’t decode the
string and give a reason why it is not decodable. Otherwise, you are not required to provide
justification.)

* 0010111010

Bits 1-2 : 00 $\rightarrow$ size = small \
Bits 3-4 : 10 $\rightarrow$ crust = stuffed \
Bits 5 : 1 $\rightarrow$ sauce = pesto \
Bits 6-10 : 11010 $\rightarrow$ toppings \
pepperoni = 1 $\rightarrow$ yes \
olives = 1 $\rightarrow$ yes \
mushrooms = 0 $\rightarrow$ no \
sausage = 1 $\rightarrow$ yes \
eggplant = 0 $\rightarrow$ no \
Decoded order 1 : size small, crust stuffed, sauce pesto, toppings : pepperoni, olives, sausage.

* 1010101010

Bits 1-2 : 10 $\rightarrow$ size = large \
Bits 3-4 : 10 $\rightarrow$ crust = stuffed \
Bits 5 : 1 $\rightarrow$ sauce = pesto \
Bits 6-10 : 01010 $\rightarrow$ toppings \
pepperoni = 1 $\rightarrow$ no \
olives = 1 $\rightarrow$ yes \
mushrooms = 0 $\rightarrow$ no \
sausage = 1 $\rightarrow$ yes \
eggplant = 0 $\rightarrow$ no \
Decoded order 2 : size large, crust stuffed, sauce pesto, toppings : olives, sausage.
