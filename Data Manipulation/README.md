# Data Manipulation Flags

This was an easier section that initially emphasized proving you could generate hashes and ended in some more challenging problems that involved the actual manipulation of data.

# Hashing - Part 1 - SHA512
**Point Value:** 5

**Prompt**
_The following challenges include some basic hashing and encoding challenges, we will also go over some basic command line tool functionality._

_Hashing is a transformation of information into a representative string. Hashes are useful because any amount of data, from a password to a DVD, can be hashed into a short string. That string will be the same, as long as the input data is the same, but if the input data is off by a little, the resulting hash is completely different. There are multiple hash algorithms, some more cryptographically secure than others._

_Hash the following in SHA512: DCDarknet_

Flag: **a648dfd38f457f7ea839b206e746a1973e32547743a3835cf53b93542bd902ae684f7f269b71c956d1f855b94df9444e33e13db2120b79a414393b05bd6e3c55**

**Methodology**
Generating common hashes can be done all over the internet, [dcode](https://www.dcode.fr/sha512-hash) provides one answer that will quickly return the desired flag.

# Hashing - Part 2 - SHA256
**Point Value:** 5

**Prompt**
_Agent, please hash the following in SHA256 and provide the output: DCDarknet_

Flag: **72eccd2a777296b367c30cbcd777e39e432c9867ad91e2f5624482feaca6cb3c**

**Methodology**
Same as the previous flag but with a different hash type, go to [dcode](https://www.dcode.fr/sha256-hash) and quickly generate the flag.

# Hashing - Part 3 - SHA1
**Point Value:** 5

**Prompt**
_In cryptography, SHA-1 (Secure Hash Algorithm 1) is a cryptographic hash function designed by the United States National Security Agency and is a U.S. Federal Information Processing Standard. SHA-1 produces a 160-bit (20-byte) hash value known as a message digest. A SHA-1 hash value is typically rendered as a hexadecimal number, 40 digits long._

_Please hash the following in SHA1: DCDarknet_

Flag: **c4bb3a44b254f5e16f610826c2d070f09697d1be**

**Methodology**
Whether the NSA designed it or not, the same method to generate a hash can be followed as previous flags, go to [dcode](https://www.dcode.fr/sha1-hash) and get the flag.

# Hashing - Part 4 - MD5
**Point Value:** 5

**Prompt**
_Next up is MD5, one of the better known hash algorithms. However, with only 128 bits of output, it is not secure. This means that it is okay to use it for other purposes, like verifying that the ISO file matches the DVD you burned, but it should be avoided for any security purpose._

_Hash the following string in MD5: DCDarknet_

Flag: **a96ea4a2eb31e4f4ffe83784484cba13**

**Methodology**
Generating a MD5 hash is no different than any of the previous flags, go to [dcode](https://www.dcode.fr/md5-hash) and get the flag.

# Hashing - Part 5 - SHA-512
**Point Value:** 5

**Prompt**
_Agent, we would like you provide the daemon with one more hash before moving on._

_Please download the file hashing_part_5.txt and provide us with the sum of a sha512 hash._

Flag: **313e3d65ee4dcca9d6c53d2af36d131042bcc944e901ff8deddf494c54abee4794f29fed1efd21c3d487453a36b8adb19b1c86ca93fc8ca792f0ae26d1631149**

**Methodology**
This is a bit different than the previous flags, in this case instead of a password hash, they are looking for a SHA-512 to fingerprint a specific file, [dcode](https://www.dcode.fr/sha512-hash) provides the solution again because it can generate hashes for files as well as strings of text. Upload the file, and generate the flag.

# Encoding - Part 6 - base64
**Point Value:** 5

**Prompt**
_In computing, a character encoding is used to represent a repertoire of characters by some kind of an encoding system. Depending on the abstraction level and context, corresponding code points and the resulting code space may be regarded as bit patterns,octets, natural numbers, electrical pulses, etc. A character encoding is used in computation, data storage, and transmission of textual data._

_Encode the following message in base64 encoding: DCDarknet_

Flag: **RENEYXJrbmV0**

**Methodology**
The decode section of the CTF involves decoding base64, in this case we will be encoding base64. Dcode can do this, as well as a wide variety of other websites. Take note, based on string length there is no equals sign on the flag. This is because equals signs are used to fill null bits in the end of the base64 string.

# Encoding - Part 7 - base32
**Point Value:** 5

**Prompt**
_Great, agent! Next up is base32 encoding._

_Base32 consists of a symbol set made up of 32 different characters, as well as an algorithm for encoding arbitrary sequences of 8-bit bytes into the Base32 alphabet. Because more than one 5-bit Base32 symbol is needed to represent each 8-bit input byte, it also specifies requirements on the allowed lengths of Base32 strings (which must be multiples of 40 bits)._

_Encode the following message into Base32 encoding: DCDarknet_

Flag: **IRBUIYLSNNXGK5A=**

**Methodology**
Converting to base32 is essentially the same as base64, and dcode provides a workable base32 encoder/decoder. The key difference when looking at the two is base32 will output as all capital letters becase base32 does not consider capitalization whereas base64 does.

# Encoding - Part 8 - Hex
**Point Value:** 5

**Prompt**
_Agent, next up is Hex encoding._

_Please encode the following and provide the output to proceed further._

_Encode the following message to Hex: DCDarknet_

Flag: **44434461726B6E6574**

**Methodology**
Converting ASCII to Hex is very simple, while dcode can do it, [RapidTables](https://www.rapidtables.com/convert/number/ascii-to-hex.html) provides a simple system for converting and additionally has really good tables for breaking out different encoding methods for ASCII. Whichever method is used, the flag is easily found. As a side note, it is important to remember that ASCII encoded as hex will always result in an even number of digits. This is because each character is encoded as 2x base16 characters (Could also be thought of as two 4-bit bytes).

# Encoding - Part 9 - Message recieved
**Point Value:** 5

**Prompt**
_We've received a message. However, we require some assistance decoding it Using some of the techniques previously used, please attempt to decode the following._

_NDQgNDMgNDQgNGUgNGMgNTcgNTEgNGQgNDUgNGIgNGMgNTkgNGQgNDUK_

Flag: **DCDNLWQMEKLYME**

**Methodology**
We know that it uses previous steps to solve the flag. While there are no equals signs, the different capitalizations suggest trying Base64 first which reveals:

44 43 44 4e 4c 57 51 4d 45 4b 4c 59 4d 45

Converted to ASCII reveals:

DCDNLWQMEKLYME

Testing this for Base32 delivers an unsatisfactory result and it does not meet the requirements for any of the other previous flags so we test it and learn it is the flag itself.

# Data Manipulation - Part 10 - Find me
**Point Value:** 5

**Prompt**
_Basic manipulation of files to locate information via various command line tools can be a very useful skill have._

_The next challenge involves some common command line tools that include grep, sort, uniq and various in order to locate information in a file provided._

_Using some included command line tools please find the unique log entry line in the file and provide the complete line to the daemon to proceed._

Note: Log attached in Part 10 subfolder

Flag: **509 Bandwidth Limit Exceeded**

**Methodology**
All roads lead to Rome, and in this case the advice in the prompt was ignored and Excel was used based on depth of knowledge in editing data within a spreadsheet. Because each error was an individual line in the log they can all be easily pasted into individual cells on Excel. Initially an attempt was made at removing exact copies but that returned a lackluster result because in many cases the errors were the same with the exception of different ports. Reloading the log and sorting A->Z found the flag almost immediately.

# Manipulation - Final - Message
**Point Value:** 5

**Prompt**
_Agent: uniq is a Unix utility which, when fed a text file, outputs the file with adjacent identical lines collapsed to one._

_Mona sent us a file titled “pithhostramen_imapoet.txt”. Please find the 5th most common line in the provided file, decode it, and provide the result to the Daemon._

Flag: **THE QUEEN OF HEARTS IS ON THE MOVE**

**Methodology**
This is another example of relying on the tools you know instead of the tools the CTF creators recommend. https://databasic.io/en/wordcounter/#paste is a very powerful tool for visually word frequency in different formats. Because each line is a continous string of characters, databasic treats each as an individual word. Loading the full txt file into the website will give a list of most common words, alternatively you can download a comma seperated value spreadsheet of all the words with word counts. Databasic ignores capitalization so you need to take the 5th most common word from the site and find one of the lines in the txt file to load. In this case it was in base64 where capitalization matters which returns the flag.
