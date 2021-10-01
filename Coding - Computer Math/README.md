# Coding - Computer Math

This section was filled primarily with basic techniques for visualizing numbers and data in different notations. This can serve many purposes and can help recognize some different ways data may be hidden during CTFs.

# bin2dec
**Point Value:** 3

**Prompt**
_Electronic circuits can only represent information using either an on state or an off state. Computer systems built on those circuits use binary to represent numbers. Instead of base 10 numbers that have a 1s place, a 10s place, a 100s place, … Binary has a 1s place, a 2s place, a 4s place, an 8s place, … The positions are 2^x._

_Using that formula, what does the unsigned binary number 1010010101101001 represent in decimal?_

Flag: **42345**

**Methodology**
Understanding the relationship between binary and decimal is an important first step because computers and their core can only rely on 1s and 0s and the human mind primarily thinks in base10. https://www.rapidtables.com/convert/number/binary-to-decimal.html will provide the flag and is often a go to option as the first Google result, but the programming mode on any computer calculator app can also convert for you.

# dec2bin
**Point Value:** 3

**Prompt**
_If you need to go the other direction and convert a decimal number to binary, you can easily do the math. But you will probably just use a decimal to binary calculator you find on the internet._

_Using either process, when you convert the 34th prime number to binary, what is the binary representation?_

Flag: **10001011**

**Methodology**
This time the flag is the reverse process as the previous one, but the number to be converted needs to be found first. When dealing with prime numbers, [dcode's](https://www.dcode.fr/prime-numbers-search) is a pretty effective tool for finding a specific prime. In this case, the flag is the prime number 139 in binary.

# hex2dec
**Point Value:** 3

**Prompt**
_Obviously it gets ridiculously tedious for people to represent numbers in binary. So they invented hexadecimal, which is base 16. Every 4 binary digits converts to 1 hexadecimal digit, which you can do in your head. But hexadecimal to decimal conversion isn't as easy._

_Convert the hexadecimal number 0xCAFEBABE to decimal by your favorite process._

Flag: **3405691582**

**Methodology**
CAFEBABE is a magic class number for Java and an awesome badge that was released for Defcon this year. https://www.rapidtables.com/convert/number/hex-to-decimal.html can answer this for us as well and will find the flag quickly. If this is your first time dealing with hexadecimal or other forms of computer notation, you need to drop the '0x' before entering it because that is just standard notation to indicate the number is written in hex.

# dec2hex
**Point Value:** 3

**Prompt**
_Decimal to hexadecimal is a conversion problem that is typically done with a calculator unless you are a savant._

_Convert the diameter of Jupiter (in km) to hexadecimal._

Flag: **0x2222C**

**Methodology**
Asking the Google brain tells us that Jupiter's diameter is:139,820 km. The flag does require the '0x' to be added which is a little unintuitive but good from the standpoint of learning relationships with hexadecimal.

# octodecimal
**Point Value:** 3

**Prompt**
_You don’t have to use bases of binary or hexadecimal. Octal was a weird blip in history that used base 8. But maybe you want to use base 18 (i.e. octodecimal) to represent numbers. Octodecimal is 18^x for each position._

_What does the octodecimal number HA11 represent in decimal?_

Flag: **102403**

**Methodology**
A programming calculator likely will not be able to do this conversion, googling will likely return a bunch of Octal (Base8) options which will not work. Searching for Base18 however will deliver multiple tools for converting between bases and find the flag. For example: http://www.unitconversion.org/numbers/base-18-to-decimals-conversion.html

# Negative Numbers
**Point Value:** 3

**Prompt**
_Eventually computer people figured out they needed to represent negative numbers in binary. There were some horrible ideas at first, such as having the MSB be a 1 for negative, or representing negative numbers as the inverse. These methods were ineffective because you had to do all sorts of complicated digital gyrations if you were actually going to add or subtract the numbers. Finally someone came up with a very elegant solution for representing numbers called “2s complement”. Basically if you want to make a number negative, you invert all the bits and then add 1. If you want to make it positive, you invert and add 1. If you want to figure out what a negative number is, you invert and add 1, remembering that it is a negative number. (Do you see the pattern)? And best of all, you don’t have to do any digital gyrations when you add or subtract positive and negative numbers. So 2s complement is cool and is the method that all microprocessors use to represent negative numbers.

What is the 2's complement digital representation in binary for the longitude of the Bellagio Fountain (rounded because we're still doing integers)._

Flag: **10001101**

**Methodology**
Longitude is looking at the East-West geographic coordinates. A quick search on Google Maps lets us know that the Bellagio Fountains are at 115 degrees West. When finding the 2s Complement you will need to use some critical thinking for a lot of convertors online because they want to look at a specific range of significant bits (often 8 or 16 bits). https://www.omnicalculator.com/math/twos-complement can find the flag for us, but you have to delete the space between the two 4-bit pairs to have the flag register.

# Big Endian
**Point Value:** 3

**Prompt**
_At some point, people figured out they wanted to represent numbers in more than one byte of memory. Therefore the question is, what order do you put the bytes. Do you put the least significant byte in the lowest place in memory, called little endian. In this case, you end up writing the number in a kind of weird backwards format, but it makes sense that you put the lower byte in the lower address. Or, do you put the most significant byte in the lowest memory location, so that it appears first. In this case, it’s kind of how you read numbers, but you’re putting the big number in the lower address. The big end first is called big endian. There is no good answer, it’s kinda weird either way. But let’s play with it._

_What is the 25th number in the Fibonacci sequence expressed in Big Endian hexadecimal format?_

Flag: **B520**

**Methodology**
The prompt has a lot of words describing Endian'ness but the thing to remember is Big Endian is how the human mind normal thinks about numbers with the most significant digit furthest to the left. We can count up to the 25th Fibonacci Number at this [link](https://www.mathsisfun.com/numbers/fibonacci-sequence.html) and learn it is 46368. Converting that normally provides the flag.

# Little Endian
**Point Value:** 3

**Prompt**
_Let's do it in a different order._

_What is the 24th number in the Fibonacci sequence expressed in little endian hexadecimal format?_

Flag: **F16F**

**Methodology**
This will be a little different from Big Endian. First, We can count up to the 24th Fibonacci Number at this [link](https://www.mathsisfun.com/numbers/fibonacci-sequence.html) and learn it is 28657. Converting it normally provides 6FF1 in Big Endian. A novice mistake would be to assume that Little Endian notation would be 1FF6, but this is incorrect. Looking at the hexadecimal, it sould be treated as bytes (pairs of hex) or in Big Endian 0x6F 0xF1. The two bytes are what is being swapped to find the flag or 0xF1 0x6F. Unlike the original dec2hex flag, this one does not require '0x' as part of the flag.

# Floating Point
**Point Value:** 3

**Prompt**
_To represent floating point numbers (numbers with a decimal in them), Beelzebub and his demons from all circles of hell were consulted to create the most inelegant solution possible. Each floating point number has a sign, an exponent, and a significand. But they also threw in things like denormalized numbers, not-a-number (NAN), representation for both positive and negative 0, representation for positive and negative infinity, overflow, underflow, and rounding methodologies to include rounding up, rounding down, round towards zero, and rounding to nearest. Thank goodness, however, they left the endianness up to the hardware manufacturers, because otherwise it would have just been way too constrained._

_In single precision floating point, what is the 32-bit hex value to represent the golden ratio to about 8 places?_

Flag: **0x3fcf1bbd**

**Methodology**
Googling Golden Ratio tells us it is equal to: 1.61803398875 which rounded to 8 places is 1.6180340. As the prompt indicates there are all sorts of options outside the scope of the problem. A short Google search for single precision floating point conversion provides a simple [tool](https://www.h-schmidt.net/FloatConverter/IEEE754.html) that outputs the flag.

# ASCII
**Point Value:** 3

**Prompt**
_ASCII is how computers represented letters and numbers so they could be printed. But that was in the days before things like emoji or unicode. ASCII only uses 7 bits to represent the numbers and letters that were needed at the time._

_What is the ASCII number (in hex) for the third letter in the fifth word from the book description of Daemon from daniel-suarez.com?_

Flag: **67**

**Methodology**
 Looking at the [site](https://daniel-suarez.com/daemonsynopsis.html) the 5th word is 'legendary' making the target letter 'g' which corresponds to the flag. Lots of ways to look this up, [RapidTables](https://www.rapidtables.com/code/text/ascii-table.html) is one option.

# UNICODE
**Point Value:** 3

**Prompt**
_Apparently people that use computers speak more than just English. So Unicode was invented to represent the rest of written languages. Unicode uses 2 bytes to represent each character._

_What are the hex values for the unicode for the following 3 letters: えもぢ (which is Japanese for emoji)?_

Flag: **3048 3082 3062**

**Methodology**
It would take a long time, but you could look each of these up in character map. Luckily google is smart, pasting each in individual into google with the term unicode will deliver the proper numbers (displayed as U+XXXX).
