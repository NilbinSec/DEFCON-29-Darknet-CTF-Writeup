# Rorschach Flags

This section was pretty easy once you found the proper source for the antenna bug splats and understood the correct format for the flags. Overall, this was a great section for people who are unfamiliar with how radio waves propagate from an antenna; it is important to recognize that different antennas behave in different ways and the cheap antenna you buy with an SDR will almost always not be the best choice for what you want to do. The biggest challenge with this set of flags was you had to find this specific file online to determine the flags: https://www.industrialnetworking.com/pdf/Antenna-Patterns.pdf. This PDF is likely the source document the CTF creators used. Many of the radio propagation patterns are similar depending on orientation and polarization and because specific propagation is very dependent on individual antenna characteristics (number of side lobes, implementation of side lobe supression, antenna lengths, number of elements, etc.). It was a little disappointing that the flags were so reliant on finding this PDF, it would have been interesting if the flag was antenna types based on common benefits or weaknesses of antenna types or factual information such as calculating gain loss from using mismatched polarization between transmitter and reciever.

A few of these were added to the annual challenge after the CTF was complete. They are included with solutions for everyone.

# Rorschach 151
**Point Value:** 8

**Prompt**
_A Rorschach (inkblot) test is used by psychologists to try and identify thought disorders in patients who are less than willing to describe their thinking processes._

_Alternatively antenna pattern charts identify those agents with other disorders....._

_Let's determine which disorder you have. Tell the nice doctor what you see._

![151](https://user-images.githubusercontent.com/85370905/134728039-04b9510e-41f0-470a-bd3d-92b30baa637f.png)


Flag: **yagi azimuth**

**Methodology**
This flag took far longer than all the other flags in the section because it was so unintuitive that the word azimuth had to be part of the flag. This was primarily because pattern charts reference a specific type of antenna; that it was a Yagi made making the connection that azimuth was required even more difficult because there are so many related names like Yagi, Yagi Array, Yagi-Uda, among others. Identifying that it was a Yagi was not difficult once the PDF was found, and it already has some of the characteristics you would expect from a yagi based on its array of multiple antenna elements along a plane. Note at this point that Yagi-based radar antennas have significantly different patters to detect aircraft at long ranges only a specific azimuth with ambiguous altitude.

# Rorschach 114
**Point Value:** 5

**Prompt**
_Tell the nice doctor what you see._

![114 (1)](https://user-images.githubusercontent.com/85370905/134731326-821da319-3991-4568-98ea-1373a40f630a.png)

Flag: **omni elevation**

**Methodology**
Finding the flag just involved looking through the PDF. Some hints based of the bugsplat shape without the PDF could be the near 360 deg coverage in elevation with asymtotic drops that represent the cone of silence directly above the antenna.

# Rorschach 142
**Point Value:** 5

**Prompt**
_Tell the nice doctor what you see._

![142](https://user-images.githubusercontent.com/85370905/134729242-52bc5b3e-c225-4a30-846f-ec35569e44c9.png)

Flag: **dipole azimuth**

**Methodology**
Similarly checking the pdf found the answer, dipoles are omnidirectional in their radiation pattern, but this may have required a guess and check during the CTF because the 5.6dBi Omni Azimuth Plane has the same pattern with reduced elevation coverage.

# Rorschach 177
**Point Value:** 5

**Prompt**
_Tell the nice doctor what you see._

![177](https://user-images.githubusercontent.com/85370905/134729719-82d4c22a-f7b2-4c9c-b220-87c892805416.png)

Flag: **patch array elevation**

**Methodology**
Found via the PDF.

# Rorschach 103
**Point Value:** 5

**Prompt**
_Tell the nice doctor what you see._

![103](https://user-images.githubusercontent.com/85370905/134729904-babda019-5273-49e4-bb88-ffc209fb84aa.png)

Flag: **patch azimuth**

**Methodology**
Found via the PDF.

# Rorschach 106
**Point Value:** 5

**Prompt**
_Tell the nice doctor what you see._

![106](https://user-images.githubusercontent.com/85370905/134730439-8903d02a-0f65-472c-a36e-a1e7c8cc5ca6.png)

Flag: **sector elevation**

**Methodology**
Found via the PDF.

# Rorschach 129
**Point Value:** 5

**Prompt**
_Tell the nice doctor what you see._

![129](https://user-images.githubusercontent.com/85370905/134730472-dded5203-87b4-4ce7-8028-5d14017d04f5.png)

Flag: **yagi elevation**

**Methodology**
Found via the PDF. This is the first flag that did not follow the elevation, azmimuth alternating pattern.

# Rorschach 131
**Point Value:** 5

**Prompt**
_Tell the nice doctor what you see._

![131](https://user-images.githubusercontent.com/85370905/134730732-188e28d7-cf01-4b84-81c4-7b0e8c89a5c2.png)

Flag: **dipole elevation**

**Methodology**
Found via the PDF. Hint is the near complete coverage with two lobes with drops to zero representing cone of silence.

# Rorschach 187
**Point Value:** 5

**Prompt**
_Tell the nice doctor what you see._

![187](https://user-images.githubusercontent.com/85370905/134730948-cef670da-3a92-4bc4-8dda-11021c113ffe.png)

Flag: **patch elevation**

**Methodology**
Found via the PDF. No good advice on recognizing this pattern because patches look very different in practice, you need the PDF to clearly connect this one.

# Rorschach 191
**Point Value:** 5

**Prompt**
_Tell the nice doctor what you see._

![191](https://user-images.githubusercontent.com/85370905/135187718-928addaa-d4cc-44e9-bb4d-4bd339c2ca73.png)

Flag: **sector azimuth**

**Methodology**
Found via the PDF. Big hint here to identify it without the PDF is the directional nature of the antenna across 180 degrees with minimal sidelobes.
