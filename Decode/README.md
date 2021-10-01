# Decode Flags

Decode was one of the easier sections. The focus was on identifying a cipher or encoding method and providing the plaintext.

# Flash drive dump - Unknown string 412
**Point Value:** 5

**Prompt**
_I am receiving floods of data from concerned agents on the ground at Cyberez. Among that data is an encoded string with an unknown cipher. Identify, decode, and submit the revealed text. There is no way to know if this piece is the one that Mona needs until exposing the data._

_What is this? jr arrq gb svaq gur yrnx naq chg n fgbc gb vg_

Flag: **we need to find the leak and put a stop to it**

**Methodology**
This was a cut and dry Caesar cipher. Boxentriq's cipher identifier correctly identified it, while https://rot13.com could have quickly been used to test and identify the proper shift, [decode's](https://www.dcode.fr/caesar-cipher) automatic Caesar tool works great as well.


# Flash drive dump - Unknown string 417
**Point Value:** 7

**Prompt**
_What is this? ZDJVZ2QybHNiQ0J3ZFhRZ1lTQnpkRzl3SUhSdklIUm9hWE1nZEdoeVpXRjBJRzl1WTJVZ1lXNWtJR1p2Y2lCaGJHdz0=_

Flag: **we will put a stop to this threat once and for all**

**Methodology**
Anytime you see a long string of alphanumerics, the possibilities are fairly small (Base64, Base32, Rot-47, ASCII85, etc.) When you see one or more equals symbols at the end that should reduce the possibilities down to just two, Base64, and Base32. Because this flag is both capital and lowercase letters, base64 should be tested first because base32 does not look at capitalization. Many tools are available for base64, when going through multiple step ciphers, NilbinSec prefers to use dcode, but in this case, https://www.base64decode.org/ works great because we are working with a single cipher.

![image](https://user-images.githubusercontent.com/85370905/129456462-45b33ed2-cb49-45ae-a537-cf5316b8a213.png)

At first this may look like a failure because there is no readable text, but if this was the incorrect method, we would expect non-readable text instead of the complete ASCII string we recieved. Even more interesting, we have another equals sign at the end. Therefore, we can operate under the hypothesis that this is Base64 encoded into Base64. Running the new string as base64 returns the proper flag.

# Flash drive dump - Unknown string 512
**Point Value:** 7

**Prompt**
_What is this? R zn hvmwrmt gsv wlli xlwvh gl blfi vnzro_

Flag: **I am sending the door codes to your email**

**Methodology**
No immediate clues about the cipher type, pasting it into [Boxentriq](https://www.boxentriq.com/code-breaking/cipher-identifier) identfies as almost certainly an Atbash cipher. Atbash does not use any form of keying, so any Atbash decoder will quickly return the flag.

# Flash drive dump - Unknown string 1011
**Point Value:** 10

**Prompt**
_What does this mean? Jfilylg giwaoxkj nsktwrfynts gsrgivrmrk wkh tgvtkgxcn Npob_

Flag: **Cyberez acquired information concerning the retrieval Mona**

**Methodology**
The final flag was the most difficult, as recognized by point value. 
Pasting it into [Boxentriq](https://www.boxentriq.com/code-breaking/cipher-identifier) identifies the possibility of a Vigenere Cipher; this is incorrect. A short attempt a bruteforcing a key returned lackluster results. With that dead end, we have to resort to more manual methods of cryptanalysis to discover the flag. One thing that stands out about this flag compared to previous ciphers in the section is the fact punctuation is included. At this point, it is worthwhile checking what might be returned as a key if we assume plaintext words such as darknet, etc. 

After vigenere attempts (including things like autokey were exhausted), expanding the scope of ideas identified that Npob == Mona in Rot-25. Using Mona and other hacker related terms related to Mona such as MonaLisa or Swordfish for keyed ciphers do not return any readable flag so other Rots are checked. Descending through rotations on https://rot13.com quickly reveals that each ascending rotatation begining at Rot-19 reveals a single word of the flag.

