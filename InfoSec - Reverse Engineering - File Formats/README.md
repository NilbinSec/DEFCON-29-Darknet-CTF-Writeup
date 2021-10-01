# Reverse Engineering - File Format Flags

An excellent section that included some previously encountered challenges. While the first question was easy albeit frustrating, the remaining flags required some enjoyable math by hand to derive the flags.

# file formats: the sounds of earth 
**Point Value:** 3

**Prompt**
_Who spoke the English greeting on the golden record that was sent on Voyager?_

Flag: **Sagan**

**Methodology**
[Wikipedia's](https://en.wikipedia.org/wiki/Contents_of_the_Voyager_Golden_Record) subpage on the greetings on the golden record state that Nick Sagan (Carl Sagan's son) provided the voiceover. Finding the flag was difficult because of an intial assumption that it would be a full name. After about 20 tries, the simpler answer turned out the be correct. The actual recording is in this repository as english.au.

# file formats: .srec
**Point Value:** 5

**Prompt**
_Motorola has a file format called an s-record or .srec. It is commonly used for programming flash memory in microcontrollers and other programmable logic devices. It uses hex values in ASCII text form to convey hex values. It is not very secure, so it is very easy to subvert and manipulate any data on any device that happens to use this format._

_Let's say we downloaded the flash memory and get this .srec:_

_S11F00007C0802A6900100049421FFF07C6C1B787C8C23783C6000003863000026_

_We want to change the functionality of the device by changing the 9th byte of data to 0x90. What do we need to change the checksum to in order to make this a valid .srec record structure?_

Flag: **2A**

**Methodology**
Wikipedia to the rescue because modifying checksums is a novel concept within NilbinSec but this (and the next flag) was really satisfying to do. The image below gives all the tools needed to solve the flag:

![image](https://user-images.githubusercontent.com/85370905/130289292-c513f14a-4bec-481b-adeb-243729b73a9d.png)

Breaking the string we recieve into individual bytes, we have the following (Note this is a bit of a simplification due to hex-byte conversion, it is not literal because the type section is not hexadecimal. For our purposes the following will derive the correct answer):
**0xS1 0x1F 0x00 0x00 0x7C 0x08 0x02 0xA6 0x90 0x01 0x00 0x04 0x94 0x21 0xFF 0xF0 0x7C 0x6C 0x1B 0x78 0x7C 0x8C 0x23 0x78 0x3C 0x60 0x00 0x00 0x38 0x63 0x00 0x00 0x26

**0xS1** identifies that this string has a 16-bit (4-bytes) address.

**0x1F** identifies the count of the remaining pairs in the record

**0x00 0x00** identifies that this record is the lowest record to be loaded into memory; there may be no other srecs associated with the file.

**0x7C 0x08 0x02 0xA6 0x90 0x01 0x00 0x04 0x94 0x21 0xFF 0xF0 0x7C 0x6C 0x1B 0x78 0x7C 0x8C 0x23 0x78 0x3C 0x60 0x00 0x00 0x38 0x63 0x00 0x00** identifies the actual data in the file. Based on the prompt above we will be modifying **0x94** to **0x90**.

**0x26** is the checksum we want to modify.

After some trial and error, it became apparent that the checksum requires the sum of all values after 0xS1. This is also stated on the Wikipedia page.

The sum of the bytes with the modification is: **08D5**. We only want the least significant byte so we drop the 08 and are left with **0xD5**.

Calculating the 1's complement we are left with **00101010** which is **2A** in hex which is our flag.

# file formats: .srec
**Point Value:** 5

**Prompt**
_Intel hex format is a file format that conveys binary information in ASCII text form. It is commonly used for programming microcontrollers, EPROMs, and other types of programmable logic devices. It is not secure, so it is very easy to subvert and manipulate any data on any devices that happens to use this format._

_Let's say we downloaded the flash memory and get this .hex file:_

_:10010000214601360121470136007EFE09D2190140 :100110002146017E17C20001FF5F16002148011928 :10012000194E79234623965778239EDA3F01B2CAA7 :100130003F0156702B5E712B722B732146013421C7 :00000001FF_

_We want to change the functionality of the device by changing the 24th byte of data to 0x30. What would we need to change the checksum of that line to in order to make this a valid .hex record structure?_

Flag: **F9**

**Methodology**
Wikipedia helped out significantly again. The key difference is we will be using the 2's complement this time to calculate the checksum.

![image](https://user-images.githubusercontent.com/85370905/130294135-8dfb89bc-c46b-4bf0-aee1-a6abd073b0f7.png)

In this case, we have five different records and want to specifically modify the 24th byte of data. The first **0x10** tells us that each record has 16 bytes of data. Therefore, we will be modifying the checksum of the second record: **:100110002146017E17C20001FF5F16002148011928**

0x10 0x01 0x10 0x00 0x21 0x46 0x01 0x7E 0x17 0xC2 0x00 0x01 0xFF 0x5F 0x16 0x00 0x21 0x48 0x01 0x19 0x28

**0x10** number of bytes in the record.

**0x01 0x10** record address

**0x00** record type; 00 means data

**0x21 0x46 0x01 0x7E 0x17 0xC2 0x00 0x01 0xFF 0x5F 0x16 0x00 0x21 0x48 0x01 0x19** data bytes; we want to modify **0x01** to **0x30** because that is the 24th byte over all (16 in first record + 8 in this record)

**0x28** checksum we want to modify

The sum of the record's bytes with the modification is 0407. We need the 2s complement of the least significant byte which is 0x07. The 2s complement is **1111 1001** which equals **0xF9** and is the correct flag. Of note, many 2s complement calculators online do not handle size of your input well and you will need to use common sense to recognize where to convert to get the correct answer. In this case, because we are looking for a 2 digit hex number, you want to take the lowest 8-bits of the calculator result as seen below:

![image](https://user-images.githubusercontent.com/85370905/130295351-193b4c26-9a96-4f0d-9939-2a543b2d99ec.png)

# file formats: blinky lights
**Point Value:** 40

**Prompt**
_What is the message encoded here?_

_Includes the included html file_

Flag: **?????**

**Methodology**
Still haven't figured this final challenge out which is disappointing because these types of challenges are right up NilbinSec's alley. We will be working together closely in hopes of solving it!
