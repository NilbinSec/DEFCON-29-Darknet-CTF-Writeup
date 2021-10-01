# Casefile Flags

This section contains all of the challenges included in the casefile a few weeks before Defcon began. A few points in the methodology will be rusty because some of the work that went into solving them was mistakenly deleted prior to Defcon not realizing that they would be needed for the write up for the actual CTF.

# Kernel
**Point Value:** 5

**Prompt**

_Kernel has a love for the Commodore 64 and Chris Pratt._

_Download the Commodore Emulator here: C64 emulator_

_In /bin, run the x64sc Commodore 64 emulator._

_Type in the attached C64 BASIC program._

_Type RUN to execute program._

_(For fun, you can use the built-in MONITOR to examine the 6502 assembly code)._

_Let the Daemon know what important communication Kernel has for you._

![c64program](https://user-images.githubusercontent.com/85370905/134783760-0f33b0a7-c021-40bd-9f09-8be103b20771.jpg)

Flag: **INTRODUCING THE DOUBLE-DECKER COUCH! SO EVERYONE CAN WATCH TV TOGETHER AND BE BUDDIES!**

**Methodology**
You can use the emulator provided. Transcribing it correctly is really important. After each line is entered you need to press Enter to load the line into memory, just building it out with the arrow keys like it is a text document will not load all the lines. If you are feeling awesome, use a real Commodore 64!

![image](https://user-images.githubusercontent.com/85370905/134783742-27b05bfa-fb4b-44f8-939c-d5063f0196e6.png)


# Sanity
**Point Value:** 5

**Prompt**

_Sanity enjoys communication at lower frequencies, typically less than 20 kHz. Her message is the name of the movie that communicated the following frequencies: 587.33 Hz, 659.25 Hz, 523.25 Hz, 261.63 Hz, and 392 Hz._

Flag: **close encounters of the third kind**

**Methodology**
Start by converting the frequencies to known sounds on the musical scale at https://professionalcomposers.com/note-frequency-chart/. This reveals a chord of: 
D(5) E(5) C(5) Mid C G(4). Googling _Song DECCG_ returns multiple hits for the movie Close Encounters of the Third Kind which is the flag.

# Gulo
**Point Value:** 5

**Prompt**

_GuloGuloDesu can communicate in multiple levels in multiple languages. He asks: 最高の武道は何ですか？ What is your answer?_

Flag: **Kung Fu**

**Methodology**
The Japanese in the prompt is easily translated to "What is the best martial art" on Google Translate. At this point, there was some guess and checking from Google for what the best martial arts in Japan were (under the impression that the Japanese of the prompt mattered). In the end, finding the flag was a matter of OSINT identifying that Gulo enjoys Kung Fu movies (source no longer available on new CTF site).

# Pyre
**Point Value:** 5

**Prompt**

_Pyre grew up on the Commodore 64._

_Download the Commodore Emulator here: C64 emulator_

_In /bin, run the x64sc Commodore 64 emulator._

_Type in the attached C64 BASIC program._

_Type RUN to execute program._

_Let the Daemon know what important communication Pyre has for you._

![pyre](https://user-images.githubusercontent.com/85370905/134783931-27653cba-4338-4c3d-9449-e17ef2a7f5b1.jpg)

Flag: **HELLO DARKNESS MY OLD FRIEND**

**Methodology**
Same as the previous Commodore 64 program. Again be careful as you input everything so it does not break the emulator.

# ZeroAltitude
**Point Value:** 5

**Prompt**
_ZeroAltitude has an unholy love for prime numbers. He has the first million memorized. To communicate in his language, you need to give the Daemon the 34293rd prime number_

Flag: **405863**

**Methodology**
Dcode has a cool [tool](https://www.dcode.fr/prime-numbers-search) for searching Prime Numbers. You want to select "Find the Nth Prime Number" option and input 34293 to get the flag.

# CmdC0de
**Point Value:** 5

**Prompt**
_CmdCode is frequently noted for saying the following phrase. What is the meaning of qoghDu'lIjDaq jIchegh?_

Flag: **i drink the tears of my enemies**

**Methodology**
Okay, as a nerd the possibility this was Klingon jumped out and became more clear when Google Translate failed to detect any languages. Searching for just _qoghDu'lIjDaq_ showed a result in the Klingon translation of Hamlet. The next step was building out the actual translation of the full phrase. Fake languages often have different interpretations and machine translation is spotty even for real languages so finding the original translator that translated the flag was crucial. Most sites use the Bing API which is not correct. Unfortunately the site used during the Casefile was not identifiable during the writing of this writeup.

# Samosa
**Point Value:** 5

**Prompt**
_Samosa has the ability to read QR codes directly. What is her message?_

![samosaQR3](https://user-images.githubusercontent.com/85370905/134784199-fcf16f46-3353-428c-9ce9-c7201529d53e.png)

Flag: **cast on 4 stitches. knit 4. knit 2, yarn over, knit across the row. repeat x46.**

**Methodology**
This is a fairly common QR code type, any modern smartphone camera will deliver the flag or you can use an online QR Code decoder by uploading the image. As a side note, this was an incredibly challenging flag. Typically, CTFs want you to go a bit beyond just a verbatim translation of a QR code, what does what you are seeing actually mean? In this case, things like knitting and stiching were tried as the flag and time was spent identifying what the actual instructions make. In this case it is a dishcloth as seen [here](https://www.diynatural.com/how-to-knit-a-dishcloth/). Finding this link was incredibly satisfying because it felt like the answer had to do with the dishcloth and made a real challenge but just wasted more time during the Casefile :).

# Mansel 
**Point Value:** 5

**Prompt**
_Mansel has the ability to read QR codes directly. What is his message?_

![ManselQR](https://user-images.githubusercontent.com/85370905/134784322-4c4db4fd-1d6a-406f-9b93-3dc04483826b.png)

Flag: **Tequila is a distilled spirit made from the Agave tequilana Weber Blue, blue agave or Agave Azul.**

**Methodology**
Similar to Samosa, this QR code can be read by most modern smartphones. Again some challenges because it seemed like there should be more to the flag beyond a literal translation of the QR code, but getting the flag was not a challenge at all.

# Lunin 
**Point Value:** 5

**Prompt**
_Steganography is the art of hiding data in other objects where it isn't obviously apparent. Lunin hid some communication in this common object. What message did he send?_

![teacups](https://user-images.githubusercontent.com/85370905/134784397-60d83540-a787-418d-bd11-b2f97848adee.jpg)

Flag: **The pirate code is more what you'd call "guidelines"!**

**Methodology**
Multiple ways to solve this one, because there is an obvious error at the top of the image and the resolution is too low for it to just be a zoomed in MSPaint edit, it is likely the image binary was edited in some manner. The Linux strings command can be a great way to search for hidden data. Often individuals hiding data in an image will do it at the end of the image after the terminator/postamble as applicable for the file format. When this happens the hidden text will appear at the end of the strings command for you. Because it is at the begining in this example, you may want to reduce the results to speed up finding what you are looking for. A command like "strings -n 10 teacups.jpg" will return all ASCII printable strings equal to or greater than 10 character which will reduce the amount of searching for the flag. If you are stuck on Windows and not using Linux, sites like http://fotoforensics.com/ will automatically provide the strings for you as part for the forensics analysis process. 

# Ohai
**Point Value:** 5

**Prompt**
_Ohai likes one-time pads for encryption, because if you don't have the one-time pad, you don't have the message. If he sends you the message: "R hyl vf accx o yrtl n frg... wznoyum pg'u dqpl." And you figure out the one-time pad is repeatedly the name of the hero of Farscape. What is the communication?_

Flag: **I try to save a life a day... usually it's mine.**

**Methodology**
Let's start with some bad news, this is not a one time pad because it repeats itself. It is a Vigenère cipher. Googling Farscape lets you know your key should be JOHNCRICHTON and any Vigenère cipher solver should quickly give you the flag.

# Krux
**Point Value:** 5

**Prompt**
_Krux loves communicating in puzzles. He recently made CONTACT with Vega and received this communication. What could it possibly mean? We have determined that the alien order of operations is always left to right. Find the value of the whorl and enter the answer in hex. It might even be code for an emoji?_

Flag: **1F596**

**Methodology**
Unfortunately most of my work on this challenge was accidentally deleted, this puzzle was so good and difficult I will not be able to invest the time to show the 100% methodology but will include some fragments of how it was solved. This was a worthwhile and befitting challenge that would not have been accomplished during Defcon had it not been for the Casefile being released a few weeks early. Within the PDF file provided are six images that can be formed into a cube with the points matched via the Arrival communication symbols as shown below:

![image](https://user-images.githubusercontent.com/85370905/134790717-1fca0a78-aab2-4ec3-ad62-458ead8de06b.png)

Once the cube is properly formed, the opposing faces are overlaid to create the actual message. The smaller font along the edge in blue is the key to decoding the values. Because it is unwieldly to use paper at this point a transition to powerpoint to build each completed page was done. The key provided the symbol for addition as well as some logical symbols like AND, OR, and NOT. From that point it was just a matter of calculating the individual symbols that are provided and combining them to calculate the value of the Wohrl that appears only once across all the pages. This was quite a tough challenge and required reworking the sides multiple times due to mirroring issues. Great work Darknet team!

![image](https://user-images.githubusercontent.com/85370905/134790832-2443d02f-dcb3-44b4-bc60-6cb3902f24be.png)


# Gateherder
**Point Value:** 5

**Prompt**
_Gateherder loves his netlists. And he sent a communication in this netlist. Let the daemon know what message you found._

Flag: **I'm going wabbit hunting**

**Methodology**
[Gerbv](https://sourceforge.net/projects/gerbv/) is a simple easy tool for viewing gerber files associated with netlists. If you run it and load all 4 .GDO files you will see the flag. (Note: The flag is easiest to read with just files 1 and 4 active)

# Ginger
**Point Value:** 5

**Prompt**
_Ginger is part machine. He has an NFC implant. He identifies as a bionic man, not a cyborg. (I guess that makes him a binary?)_

_If you want to communicate with Ginger electronically, what frequency would you use?_

Flag: **13.56 MHz**

**Methodology**
Googling "NFC Implant Frequency" returns the flag right away.

# Bunni
**Point Value:** 5

**Prompt**
_Bunni communicates in pure digital waveforms. He has included several formats depending on your preference. What is his message?_

Flag: **No one here is exactly what he appears - G'Kar**

**Methodology**
First we need to be able to read these files. [GTKWave](http://gtkwave.sourceforge.net/) is a great option and can parse the .VCD file. I found having zoom set to where the labels are around 100 picoseconds worked great because the individual bits are 10ps each. GTKWave lets us know we are looking at a UART signal and the file name tells us something is asynchronus about the signal. UART uses a '1' bit as the null signal on the line when no data is being transmitted and uses a single '0' bit to then indicate that data will be transmitted. Below is a screenshot of the first byte of the signal:

![image](https://user-images.githubusercontent.com/85370905/134785038-2c015116-4f03-4cdd-a17b-5cce5ea54a67.png)

The first two lines show the final stop bit followed immediately by the start bit. Then, 8 bits follow before a stop bit that continues as a null until the second byte is transmitted. The UART is transmitted in little endian so the desired byte is '01001110' or 'N'. While it takes a while, going through the entire signal carefully reveals the flag. It does not appear possible to automate this because the timing of the pulses is so short that most programs will not recognize it as a valid signal sample.

# Nolen
**Point Value:** 5

**Prompt**
_Nolen communicates electronically in pure digital waveforms. He has included several formats for your decoding enjoyment. What is his message?_

Flag: **Next time you want to stab me in the back, have the guts to do it to my face. - Mal**

**Methodology**
GTKWave again works great to get this flag. This time GTKWave lets us know we are looking at a MOSI signal with associated CLK signal for timing. Again, 100ps is a good scale to set because the CLK signal bits are in 10ps steps. While this is a digital signal given the right angles, you are looking at center of the CLK '1' bits to determine what the corresponding MOSI bit should be. Below is the first byte:

![image](https://user-images.githubusercontent.com/85370905/134785215-bd561db9-9311-4e57-bbac-ae103a2fec4d.png)

Again, MOSI is transmitted in little endian so the byte we are expecting is 01001110 which again is "N" in ASCII. Finishing the full signal provides the flag.

# Skyria
**Point Value:** 5

**Prompt**
_Where would this image seem to indicate that Rune is from?_

![rune](https://user-images.githubusercontent.com/85370905/134790337-19d5611e-7625-4f3c-8fe6-fca2766100c6.jpg)

Flag: **Ontario**

**Methodology**
Quickest way to get to solving this flag is to use ExifTool, something that is worthwhile to do early on when evaluating any image during a CTF. Alternatively, there are plenty of websites that will pull metadata from an image for you. Whichever way you get the metadata, the following location for the image is provided: 51.497357 degrees N, 86.631106 degrees W. Decimal degrees works well in Google Maps. As formated it will be: 51.497357, -86.631106 (you need the minus symbol because west is to the left of the Prime Meridian. Similarly if it was 51 degrees south you would use a minus symbol as well because it is below 0 degrees on the Equator. Zooming out on Google Maps shows which province is the flag.

# Rune
**Point Value:** 5

**Prompt**
_Skyria is our resident story teller. Her communication protocol is through the written word, and she excels at it. She is one of the people responsible for the Darknet story as it has evolved over the many years._

_According to the Darknet Lore, what was the name of the archivist organization?_

Flag: **Moeity**

**Methodology**
Pretty simple flag with just some reading of the [Lore Page](https://darknet-ng-continual.ctfd.io/lore) on the CTF required to find the flag.

# McL0v1n
**Point Value:** 5

**Prompt**
_McL0v1n had a setback this year in preparation for Defcon. What was his setback?_

![mcl0v1n](https://user-images.githubusercontent.com/85370905/134785331-f449e250-8cfd-48da-857b-406dda1cc9a1.jpg)

Flag: **i just melted my server rack**

**Methodology**
This is a 1D style barcode. Lots of different barcode decoders online [Link](https://online-barcode-reader.inliteresearch.com/) can find the flag easily.

# Gourry
**Point Value:** 5

**Prompt**
_When looking at the Darknet 8 badge code There is a "Over The Air" update access point hard coded into the badge. What was the previous port number it's looks for, to pull the update from, before the final firmware version?_

Flag: **8070**

**Methodology**
We need to do some digging on github for this one. Searching for OTA on the DC Darknet 8 Badge [repository](https://github.com/thedarknet/darknet8-badge) shows there used to be quite a few things deleted from the current repo. With a bit more digging and looking at reversions we can find the port number and when it was changed below:

![image](https://user-images.githubusercontent.com/85370905/134785459-33afce0c-9f91-461d-a990-66932e8968e0.png)

# Gater_Byte
**Point Value:** 5

**Prompt**
_Gater_Byte has been working with Digital_Tinker on the Holon Network Podcast where they cover vulnerability, sercurity, privacy, personal projects, and cools tools._

_They will also be streaming live remotely on twitch durring DEFCON on their Holon Network Twitch_

_They also have dropped hints for Darknet projects._

_When did they start reporting on the DOGECOIN price?_

_Submit the anwser as yyyy-mm-dd._

Flag: **2021-04-19**

**Methodology**
Sorry Gater_Byte, this was solved via guess and check. Dog Money got hot to talk about around March/April of 2021 so finding the flag was a matter of loading up the lists of podcasts and checking each date a podcast was published until the correct one was hit.

# blakhal0
**Point Value:** 5

**Prompt**
_blakhal0 likes things hot, and spicey! As part of his peppercon contest, what software was his Multi-User-Dungeon (MUD) built on?_

_This might require doing some Open Source Intelligence Gathering._

Flag: **Evennia**

**Methodology**
OSINT is the hint so that is what we will go with. Googling "blakhal0 MUD" returns a tweet with the flag as the first result:

![image](https://user-images.githubusercontent.com/85370905/134785533-6729e9d0-ab0e-4cc8-83ee-b0439f4f096a.png)

# Kaosaur
**Point Value:** 5

**Prompt**
_What technology stack is Kao very comfortable with?_

_He left a clue in the form of the file attached._

_You should be able to check for a hint, or do some Open Source Intelligence Gathering to get this answer._

![kao_clue](https://user-images.githubusercontent.com/85370905/134785577-a350a023-9aac-4af0-b16e-35987a88b42b.png)

Flag: **HashiCorp**

**Methodology**
The clue is a message in Braile. Decoding it with https://www.brailletranslator.org/ provides the flag. (Note: There are several standards for braille, if you encounter this in other CTFs and it just is not working, consider trying a different standard beyond the common English 2 standard) 

# Envelope
**Point Value:** 5

**Prompt**
_Envelope is the bionic woman. She has a T5577 RFID implant in her hand. One day she "happened to find" an RFID card to a door she has been wanting to get in. She scanned the card with a Proxmark3 RFID Reader/Writer and found that it is an HID card with an ID of 2006db2203. What command would she use in the Proxmark software to clone the card onto her RFID implant?_

Flag: **lf hid clone 2006db2203**

**Methodology**
This [cheatsheet](https://scund00r.com/all/rfid/2018/06/05/proxmark-cheatsheet.html) for the Proxmark3 was used to identify the proper flag when combined with the HID card ID from the prompt.

# Silk
**Point Value:** 5

**Prompt**
_Silk ( aka Alex ) has been streaming on youtube and twitch since Nov 20, 2020._

_He has done some awesome videos from HACKING DEFCON with a URINAL CAKE to Unofficial DEF CON 29 Badges #badgelife._

_He also hosts a weekly "Hacker Hangout" and is trying to stream LIVE from DEFCON, He needs 1000 Subscribers to do that live from mobile._

_He would love you to like and subscribe, But what is the last thing he says before he closes his videos?_

Flag: **hack on**

**Methodology**
This required a little bit of guess and checking because of a lack of familiarity with Silk's channel. After watching a few episode ending scenes the correct flag was found.
