# Strange Signals Flags

This section was all about Slow Scan TV, and for those that were not familiar with the classic preamble tones that indicate an inbound SSTV signal, the Darknet crew provided some very strong nudges early in the chain of problems. Overall, this was a pretty challenging set of flags from an in-person Defcon point of view. The computer that was at Defcon was pre-set up for SSTV and difficulties getting RX-SSTV/qsstv to work made it very difficult because the software wouldn't acknowledge the sound when the mp3 file was played. To solve this, most of the SSTV frames were interpreted via the SSTV iOS phone app (Android has several similar options). An additional consideration was the sheer length of the SSTV mp3 at just over one hour. In a non-time constrained environment, it would probably make sense to chop most of the signals into individual mp3s just to manage the identification of SSTV encoding. Because time is of the essence in any CTF, this actually added a significant challenge as the SSTV frames of interest got later and later into mp3. For the purposes of the SSTV decoded images included here, some are from the iPhone app, and a few are from much clearer sources that were found after the CTF to make it easier to read; realize that during a CTF you should be looking for the minimum viable solution which may show very little intelligible text. 

# Strange Signals 1 
**Point Value:** 10

**Prompt**
_We have some strange signals we want you to look at._

_You will need to download the attached file located at https://goo.gl/nco8RG. Mona, the triple agent who was working for us in the Mad Hatter's camp, was able to sneak us an audio file before she was discovered. The file seems to be encoded, however._

_How is it encoded?_

Flag: **SSTV**

**Methodology**
Knowing what the preamble of SSTV sounds like is crucial at this stage, that being said, the wording of the prompt along with one of the widely available signal identification sites would make this pretty easy to solve too.

# Strange Signals 2 
**Point Value:** 2

**Prompt**
_There are various applications available for Android, iOS, Windows, Mac, and Linux to decode SSTV. Find one that works with your device. (If you have Kali, qssrtv is a good application to start with. Connect your laptop to the internet and, in your terminal, type "apt-get install qsstv -y". Once installed, you can use it by typing "qsstv" in your terminal.)_

_Try decoding your first file with your SSTV application._

_When you are ready, tell the daemon Ready_

Flag: **Ready**

**Methodology**
Flag was in the instructions, just a step intended to prepare you for the difficult ones to come.

# Strange Signals 3 
**Point Value:** 10

**Prompt**
_The slides now need to be decoded. I hope you're still willing to help because it's going to get complicated, as every slide is in a different SSTV encoding. To get started, the first sequence looks like it's using the "Martin1" encoder. Once decoded, what does the bottom text say?_

Flag: **DATALOGGER1**

**Methodology**
Running the first SSTV signal revealed the following image:

![image](https://user-images.githubusercontent.com/85370905/133945698-1e749f79-b870-4d9f-937b-ec2685f527f5.png)

Flag is right where the prompt says.

# Strange Signals 4 
**Point Value:** 10

**Prompt**
_Just like in Metropolis, what can't you stop? Make sure you’re checking the slides._

Flag: **AN IDEA**

**Methodology**
Running the next SSTV signal revealed the following image:

![image](https://user-images.githubusercontent.com/85370905/133945732-81044fea-6276-4580-bc4b-3aa28d51058c.png)

The metropolis vibe really stands out on the image so we know we are in the right place.

# Strange Signals 5 
**Point Value:** 5

**Prompt**
_Now that you are starting to learn the terminology, what are the Daemon communities called?_

Flag: **holons**

**Methodology**
Pulled from this image:

![image](https://user-images.githubusercontent.com/85370905/133945792-e306c96d-7277-409c-8eae-c0b8551457d9.png)

As a side note, the point value probably drops on a few of these because they are somewhat guesssable/findable on DC Darknet sites.

# Strange Signals 6 
**Point Value:** 5

**Prompt**
_What is a part of this newly formed community?_

Flag: **reputation**

**Methodology**
Pulled from this image:

![image](https://user-images.githubusercontent.com/85370905/133945918-b6102b02-9f8a-4085-801d-47551b805fad.png)

As an example of what actually solved this step, this is the image that was decoded during the actual CTF and is not nearly as clean as it could/should have been for a skilled HAM radio operator:

![image](https://user-images.githubusercontent.com/85370905/133945910-a338cf6a-ffb0-4545-9a7f-b35a896a32d6.png)

# Strange Signals 7 
**Point Value:** 5

**Prompt**
_As we become more self sufficient, encouraging and creating, we know that the “holons are BLANK”_

Flag: **coming**

**Methodology**
Pulled from this image:

![image](https://user-images.githubusercontent.com/85370905/133945990-94536d11-abda-4faf-bc64-03c582ed665e.png)

Around this point, it was getting increasingly difficult to manage which signals needed to be decoded better to find the correct flags.

# Strange Signals 8 
**Point Value:** 10

**Prompt**
_What is the last thing on the slide?_

Flag: **end-of-transmission**

**Methodology**
Pulled from this image:

![image](https://user-images.githubusercontent.com/85370905/133946026-f90537be-2068-4b37-8771-3b0d7165b84a.png)

Below is another example of an intermediate step during the actual CTF. It is super unclear, but the flag can be determined via some critical thinking about the flag and what should come last; in this specific case, modifying the phase of the return made it a bit clearer and made the hyphens apparent:

![image](https://user-images.githubusercontent.com/85370905/133946050-c7d9f5aa-5a59-45cc-81e7-ec36789f67ef.png)

# Strange Signals 8 
**Point Value:** 14 (At end of CTF)

**Prompt**
_This last one looks like it is going to be different, you might have to think more down the lines of old communication methods… If you can decode it, Follow the Instructions._

_What is it an image of?_

Flag: **Daemon**

**Methodology**
This final challenge is not SSTV, it is actually an old encoding format for fax. The initial hunch was based on: https://www.sigidwiki.com/wiki/Meteosat_WEFAX and while the HFFax app did return something more than random noise it was not a SATCOM based signal. Eventually the following image was found via the raw mode on Robot36":

![image](https://user-images.githubusercontent.com/85370905/133946164-fe8600b4-2f49-45fb-8362-ab4807eea9ee.png)

Following the directions, Gater Byte kindly provided the flag.
