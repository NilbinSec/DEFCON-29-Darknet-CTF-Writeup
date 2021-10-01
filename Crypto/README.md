# Crypto

A fun short set of flags related to different types of cryptography. This is a strong skill for NilbinSec! Make more of these :)

# Cipher
**Point Value:** 3

**Prompt**
_Let's play with some ciphers. What is the translation for the following text?_

_Bu, lbh pbhyq qb gung, ohg V pbhyq anvy lbhe urnq gb n gnoyr, frg sver gb vg, naq srrq lbhe puneerq erznvaf gb gur Cnx'Zn'En. Ohg vg'f na vzcresrpg jbeyq naq jr arire trg rknpgyl jung jr jnag._

Flag: **Oh, you could do that, but I could nail your head to a table, set fire to it, and feed your charred remains to the Pak'Ma'Ra. But it's an imperfect world and we never get exactly what we want.**

**Methodology**
With the time crunch of a CTF, a site like [Boxentriq's Cipher Identifier](https://www.boxentriq.com/code-breaking/cipher-identifier) is a good first step which identifies this as a probable Caesar Cipher. Dcode.fr's Caesar tool will test all the possibilities and identify the most likely permutation which revealed the flag. In this case, it was actually a subset of Caesar called Rot13 which is probably the most common type of monoalphabetic substitution cipher.

# Caesar Cipher
**Point Value:** 3

**Prompt**
_This one uses a process that is slightly more generic than a ROT13 cipher. Can you provide the translation for the following text?_

_Aol mbabyl pz hss hyvbuk bz, dhpapun pu tvtluaz vm ayhuzpapvu av il ivyu pu tvtluaz vm ylclshapvu. Uv vul ruvdz aol zohwl vm aol mbabyl vy dolyl pa dpss ahrl bz. Dl ruvd vusf aoha pa pz hsdhfz ivyu pu whpu._

Flag: **The future is all around us, waiting in moments of transition to be born in moments of revelation. No one knows the shape of the future or where it will take us. We know only that it is always born in pain.**

**Methodology**
Being told up front we are dealing with a Caesar Cipher makes it really simple. Dcode identifies that a +7 shift is the only intelligible plaintext.

# Hash
**Point Value:** 3

**Prompt**
_SHA-1 (Secure Hash Algorithm, 1st version) is an algorithm which converts a given sequence of characters into another unique sequence of characters, with a fixed length, called "hash"._

_SHA-1 hashes are theoretically impossible to reverse directly, ie, it is not possible to retrieve the original string from a given hash using only mathematical operations._

_Most web sites and applications store their user passwords into databases with SHA-1 encryption. This method appears to be safe as it seems impossible to retrieve original user passwords if, say, a hacker manages to have a look at the database content._

_What is the SHA-1 hash for:_

_There isn’t enough life on this ice cube to fill a space cruiser_

Flag: **1044d766bc542b69f2aebfd54504610a07bac1f3**

**Methodology**
Dcode provides a [SHA-1 Hasher](https://www.dcode.fr/sha1-hash) which works great for solving the flag.

# Decryption
**Point Value:** 5

**Prompt**
_If you know a block of text was encrypted with a Vigenère Cipher, and you know the shift key is starts with GQu ..., but you're not sure how many characters, and what the next ones are._

_Translate the following text:_

_Zxyfr oi u uekqnse jqlyakim hugd nvr udy kr lyavg. Oj cg gnu xoeqdygf uv nvr yeoz gnqn vny bigg ojm kne. Jbs jgh qs sowbh vy dih nmqcbfz fikrxi ubq vhcbpofuzvzyyg, vz ym otgyhgg ixucf gdx rryfuwe. Mhyogkh nvnt jbs qkqnv bl vfsfn ym huk tyogn ez vbvu, nvr juuhu uv xfrgcm. Otgyhgg zxcg ckhcz jk sub aklyf fahlsajul._

Flag: **There is a greater darkness than the one we fight. It is the darkness of the soul that has lost its way. The war we fight is not against powers and principalities, it is against chaos and despair. Greater than the death of flesh is the death of hope, the death of dreams. Against this peril we can never surrender.**

**Methodology**
Because we already know it is a Vigenère Cipher let's jump right back to dcode and use their [Vigenère Cipher Tool](https://www.dcode.fr/vigenere-cipher). You could solve with the partial key provided, but equally you can start with just testing the automatic bruteforce (Which also solves this super quickly). The key is GQUON. (Note: The prompt has both lower and uppercase letters, this is inconsequential to Vigenère Ciphers which do not care about lettercase)

# Rainbow Tables
**Point Value:** 5

**Prompt**
_Computers don't store user names and password in a password.txt file. Instead they store the HASH of the password. You can't go backwards from the hash to arrive at the password. However, you can compare the stored hash with a hash of what a user types in for his password. If they are equal, then the user typed in the correct password._

_(un?)fortunately, some people use common passwords. Some of these common hashes are found on the internet with the corresponding password. Let's say you look at the fabled PASSWORD.TXT file and it has the hash of a password as:_

_02726d40f378e716981c4321d60ba3a325ed6a4c. What is the password?_

Flag: **Pa$$w0rd**

**Methodology**
https://crackstation.net/ is a site that returns results from a wide variety of rainbow tables for different hashing standards and returns the flag immediately. While this flag only needs a simple rainbow table lookup, it is worthwhile to discuss some points about attacking hashes for situations when it is more complicated or you have to turn to some sort of hashing program like Hashcat to get the flag. Sites like https://www.tunnelsup.com/hash-analyzer/ can look at the size and composition of a given hash and tell you what type of hash it most likely is. For this hash, it identifies it as most likely SHA-1 (Which is correct) but also points out that it meets the requirements for SHA-128. If you were going to brute force this password you would possibly need to try both. This password is weak and easily bruteforceable as well. Remember that programs like hashcat can easily test dictionary attacks with leetspeak conversions. 
