# Analog Electronics 102

Moving up in difficultly from Analog Electronics 102, this section was great! It required a skill people should actively develop if they have not previously--the interpretation of charts. Being able to extract information from charts is crucial to being able to understand the real world and how objects perform for a given situation.

# EE102 with Gateherder
**Point Value:** 0

**Prompt**
_Great job getting this far, agent! @gateherder is watching your progress with interest! Let's see if we can't dive a little deeper.._

_Let's start the next section. Enter dive a little deeper in the daemon_

Flag: **dive a little deeper**

**Methodology**
The first flag is just a gatekeeper to unlocking this set of challenges.

# EE102.1.1 Datasheet Diving
**Point Value:** 5

**Prompt**
_When setting out to design a circuit, the best place to start is the datasheets. You may not need a datasheet for a quick test circuit on a lab bench, but if you’re producing a circuit that needs to work every time for many years, especially if you’re getting paid for the circuit to work, there are nuances that must be considered. Datasheets are where we learn about many of these nuances. Let's get started!_

_Everyone loves LEDs, so let’s use an LED datasheet as our first example. In fact, our friends at Adafruit have already put together a great tutorial on the topic of LEDs! The following questions are designed to introduce you to component datasheets, what you can find in them, and how to read them. (HINT .... start here: https://learn.adafruit.com/all-about-leds)_

_The LEDs in the tutorial are made using multiple dominate chemicals. Name those chemical(s), or their chemical compound (e.g. table salt would be either “Sodium Chloride” or "NaCl")_

Flag: **Gallium Aluminum Arsenide**

**Methodology**
The link in the prompt is a good hint because it provides a link to the specific LED we care about. Clicking on "The LED Datasheet" provides a new webpage with a link to the PDF we need [Linked Here](https://cdn-shop.adafruit.com/datasheets/WP7113SRD-D.pdf). The first page of the datasheet provides the following description: "The Super Bright Red source color devices are made with Gallium Aluminum Arsenide Red Light Emitting Diode.", which provides the flag.

# EE102.1.2 Datasheet Diving
**Point Value:** 5

**Prompt**
_Which polarity is represented by the shorter of the two legs?_

Flag: **negative**

**Methodology**
Okay, this is a weaker flag because there was no punishment for guessing in the CTF. You could just check negative and positive and probably get the flag correct with zero searching or understanding of how LEDs work. That being said, on the first page is the below image:

![image](https://user-images.githubusercontent.com/85370905/134777677-6c1df504-84e9-4456-8299-b890fa6f70d5.png)

The shorter leg is labled as the Cathode. Googling cathode lets you know: the negatively charged electrode by which electrons enter an electrical device. Quick and easy flag.

# EE102.1.3 Datasheet Diving
**Point Value:** 5

**Prompt**
_What percentage of the maximum intensity is seen at 20 degrees off-axis (aka 20 degrees away from “direct viewing”)? (e.g. "7%")_

Flag: **40%**

**Methodology**
This was a great flag because it required interpretation of charts to get correct, though it is a bit disappointing that it had the same point value of the previous two datasheet flags. Page three has a variety of charts that provide information on the LEDs for a given situation. We are concerned with the final chart on spatial distribution provided below:

![image](https://user-images.githubusercontent.com/85370905/134777823-17e223d3-5b78-446f-85f5-fe4741f0e597.png)

This chart looks a bit different from all the others. The concentric rings are the given intensities of the LED, the radial lines are different degrees off-center for viewing the LED, and the ellipse represents the LED strength. We can get the flag by looking at where all 3 components intersect. At the 20 degree radial, the LED ellipse intersects with the unlabled 0.4 line (we know each line is a 0.1 step based on the two labled lines 1.0 and 0.7). Converting 0.4 to a percentage gives us the flag.

# EE102.2 Noisy Neighbors
**Point Value:** 5

**Prompt**
_Most modern circuits are complex and noisy. Motors turning on and off, LEDs flashing, speakers buzzing, etc. No power supply is perfect, and must balance efficiency (the overall cost to operate) with instantaneous capability. Momentary voltage sag can occur when a particular part of a complex circuit design needs lots of quick power but it isn’t available. Graphing the resulting “available power” in the system over a period of time will look like a choppy ocean during a storm, swelling and jumping both up and down, almost whimsically. What can steady such a tumultuous electrical storm? What can hold power in reserve for when we need it? Our good friend the capacitor, of course!_

_Big caps hold lots of power but cannot store or release it quickly. Small caps can operate very quickly but cannot hold much energy. The ability to gather and release energy of different magnitudes and at different frequencies are represented in an impedance chart, which is a graph of resistance (Y axis) versus operating frequency (X axis). These charts can be found in-- you guessed it-- the capacitor datasheet! Murata (a capacitor manufacturer) has a nice write-up. Check out Figure 4 of this link: https://www.murata.com/en-us/products/emiconfun/capacitor/2013/02/14/en-20130214-p1 ._

_Every capacitor is most effective when operating at its "self-resonant frequency," but interestingly develops another parasitic property when operating higher than it's self-resonant frequency. What is this higher region called?_

Flag: **inductive region**

**Methodology**
Using the link provided in the prompt, we can find the flag. Once you hit the section _Near the Resonance Point_, a description of the inductive region qucikly reveals that it is the flag. "The region below the self-resonant frequency is called the capacitive region and the region above is called the inductive region."

# EE102.3.1 Derated for Life
**Point Value:** 5

**Prompt**
_We learned earlier that ideal components don’t exist in the real world, and that in the real world things become more complicated due to parasitics. We also learned that component datasheets contain a multitude of useful information (by comparison, LEDs are among some of the simplest components). Another complicating factor is temperature._

_Let's revisit that LED datasheet from earlier (https://learn.adafruit.com/all-about-leds). There is a particular chart called the “Derating Curve.” In this chart, Vf, or Forward Voltage, is derated based upon operating temperature. What this means is that if you want the device to “survive” and operate for long periods of time without burning out or becoming significantly dimmer, then you need to be aware of how hot it will be in which the LED will be operating, and adjust your circuit design accordingly. (Hint: the derating curve will look like this: https://goo.gl/5W7jVH)_

_How much current can you safely sustain through the LED if its ambient temperature reaches 75 degrees Celsius?_

Flag: **10 mA**

**Methodology**
Another awesome opportunity to interpret charts! Back on page three of the PDF from EE102.1.1 we can see that only one of the charts includes temperature and current on the X- and Y-Axis, so we should start there.

![image](https://user-images.githubusercontent.com/85370905/134778248-d7c31adf-2d70-479e-93cf-23e81030d737.png)

Because there is no line for 75 degrees celcius, a little bit of estimation is required, but moving up to where the LED's line crosses and checking the Y-Axis, we can be confident the flag is 10 mA.

# EE102.3.2 Derated for Life
**Point Value:** 5

**Prompt**
_When properly derated for an ambient temperature of 75C, how bright will your LED be (typically) when viewed 10 degrees off axis? (hint: you'll need to combine several charts for the right answer) (e.g. “10mcd”)_

Flag: **87.5mcd**

**Methodology**
This is an awesome flag and it ramps up the difficultly in a way that you would expect more points to be awarded. First, we need to determine which charts are required; points we are concerned about are ambient temperature (in Celsius), Viewing angle, and luminosity. Looking at the charts, luminosity is the common frame of reference and the following two will be needed:

![image](https://user-images.githubusercontent.com/85370905/134777823-17e223d3-5b78-446f-85f5-fe4741f0e597.png) ![image](https://user-images.githubusercontent.com/85370905/134778755-0963bee1-50d0-42c3-8de2-73d4a3f2803f.png)

First, at 10 degrees off-axis, we have 0.7 modifier for luminosity. Second, at 75 degrees Celcius, we have a 0.5 modifier for luminosity. With these two modifiers, we need to figure out how to find the correct units/values to modify. The unit 'mcd' (millicandela) only appears on page two and lists a typical luminosity of 250 mcd at 20 mA. Because the prompt does not discuss current or power on the LED, we should use this typical luminosity for the problem. 250 * 0.7 * 0.5 = 87.5. Adding the correct units, mcd, to the end of our answer provides the flag. 
