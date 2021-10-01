# Analog Electronics 101

An enjoyable section with fairly easy flags to find, it did a great job of building some initial skills for the later Analog Electronics sections in the CTF.

# EE101 with Gateherder
**Point Value:** 0

**Prompt**
_Electrons flow in circuits, enabling simple blinky lights, to complex DEFCON electronic badges, to the Daemon itself. Let’s skim the surface and start to understand a little bit more about how this "electronic stuff” actually works._

_Type skim the surface to start_

Flag: **skim the surface**

**Methodology**
The first flag is just a gatekeeper to unlocking this set of challenges

# EE101.1 - Intro to Electronics
**Point Value:** 3

**Prompt**
_Electronic circuits are composed of one or more components interconnected to perform specific functions. Some components are uncommon and esoteric, but others are common and actually make up most circuits._

_Electrical components are largely divided into two groups: Passive (those that do not provide a source of energy) and active (those which can provide electrical power to downstream circuitry)._

_Passive components typically include components such as resistors, capacitors, and inductors._

_Active components include components such as transistors, vacuum tubes, integrated circuits, etc._

_There are other types too, like electro-mechanical components such as crystals, piezoelectric devices, and switches. A great resource to start learning about the many types of electronic components can be found at: https://en.wikipedia.org/wiki/Electronic_component ._

_What is the component used to maintain a steady output voltage? This component works by varying the resistance with the load resulting in a constant voltage output. It is commonly used when clean, "low noise" voltage is more important than "efficiency."_

Flag: **Linear Regulator**

**Methodology**
Unfortunately, the Wikipedia article in the prompt did not help too much finding the answer. Instead, Googling "what component is used to maintain a steady output voltage" points us to the voltage regulator page on Wikipedia. That Wikipedia page discusses several types with a linear regulator fitting the flag most closely. A linear regulator is: a system used to maintain a steady voltage. The resistance of the regulator varies in accordance with both the input voltage and the load, resulting in a constant voltage output. 

# EE101.2.1 - On the Shoulders of Giants
**Point Value:** 3

**Prompt**
_We're on our way! But we cannot in good conscience proceed without first tipping our hats to some of history's greats: Jean-Baptiste Joseph Fourier, Alessandro Volta, Hendrik Wade Bode, Sidney Darlington, Michael Faraday, Heinrich Rudolf Hertz, Nikola Tesla, James Watt, Joseph Foruier, Michael Faraday, Joseph Henry, and Thomas Edison, just to name a few (there are so many more!)._

_After whom (first and last) is this fundamental electricity equation named: Voltage = Current * Resistance_

Flag: **Georg Ohm**

**Methodology**
Hopefully, you recognize the equation in the prompt as Ohm's Law. Even if you do not, the rule is so basic that typing it into Google will return the answer Ohm's Law, from there it is just a Wikipedia search to find Ohm's first name, which is Georg.

# EE101.2.2 - On the Shoulders of Giants
**Point Value:** 3

**Prompt**
_Who (first and last) is credited with discovering the principal that “the sum of electric currents which flow into any junction in an electric circuit is equal to the sum of currents which flow out"_

Flag: **Gustav Kirchhoff**

**Methodology**
You either knew this was Kirchoff's Law or you googled the principal in the quotes and found his first name on Wikipedia.

# EE101.3 - Schematic Symbols
**Point Value:** 3

**Prompt**
_Like any subject matter or language, electrical circuit design has its own grammar. Commonly that grammar is a graphical representation of electrical components and how they are interconnected. We call this graphical representation a schematic, or wiring diagram. In order to design (or reverse engineer!) a schematic, we need to learn the visual symbols used to represent the components. Check out this link for more information: https://en.wikipedia.org/wiki/Circuit_diagram ._

_What is the name of the component represented by this symbol: https://bit.ly/2Z4AEEn ._

**Note: the google drive the Bitly points at is currently unavailable; this is what the symbol is:**

![electronic-symbol-loop-antenna-electronics-aerials-png-favpng-00vZGKi2u9t3Mraqt1QaAwNTb](https://user-images.githubusercontent.com/85370905/134776712-6e310765-eb95-4ef9-b88d-5905f4919a35.jpg)

Flag: **Loop Antenna**

**Methodology**
Lots of options to solve these types of flags. Google can return lots of websites that contain a wide variety of different charts showing different schematic symbols, Wikipedia provides a decent starting point at: https://en.wikipedia.org/wiki/Electronic_symbol

# EE101.4 - Schematic Symbols
**Point Value:** 3

**Prompt**
_A clearly drawn schematic may facilitate understanding of circuit operation, but sometimes a pretty schematic does not necessarily capture the best way to physically create the circuit onto a printed circuit board (PCB). Often, the components themselves are wired in ways that don't initially make much sense (a great example is the classic https://www.ti.com/product/LM3900 quad op-amp)._

_What is the most common name for the data format used to convey the necessary circuit wiring information between a schematic design tool and a PCB layout tool?_

Flag: **netlist**

**Methodology**
Inexperience shined through on this flag because gerber file stood out as the answer initially, which is incorrect. Gateherder's casefile was the nudge that was needed to figure out the flag, with a quick googling of the term to confirm.

# EE101.5 - Less than Ideal
**Point Value:** 3

**Prompt**
_To simplify learning and analysis, most components are typically assumed to be "Ideal." An ideal resistor only has resistance and an ideal capacitor only has capacitance. In the real world, however, a resistor may include stray or “parasitic” inductance, or even a small amount of capacitance (depending on things like how it is produced, packaged, and put onto a printed circuit board (PCB)). In the real world, high performance circuit design can be quite tricky!_

_What is the most common name of another real world phenomenon wherein an electrical signal can "hop" from the desired wire to an undesired wire through parasitic capacitive coupling? (This most commonly happens when the two wires are physically located too close to one another.)_

Flag: **crosstalk**

**Methodology**
The operative term to search for from the prompt was "parasitic capacitive coupling", which would lead you eventually to a wide variety of potential solutions such as https://techweb.rohm.com/knowledge/emc/s-emc/01-s-emc/6943#:~:text=Crosstalk%20is%20the%20transmission%20of,and%20is%20also%20called%20interference.&text=Coupling%20between%20lines%20can%20be,resulting%20from%20the%20mutual%20inductance.

# EE101.6.1 - Vacuum Tubes
**Point Value:** 3

**Prompt**
_When having trouble understanding transistors as a youth, @gateherder’s dad gave him a book called “Elements of Radio” (Marcus & Marcus, 3rd ed, 1953), which did a masterful job of explaining vacuum tubes from scratch. Vacuum tubes were used in everything from aircraft to xray machines, and televisions to electronic clocks. In fact, the “triode” vacuum tube is arguably the foundation of the modern electronics revolution! For more information, check out this link: https://en.wikipedia.org/wiki/Vacuum_tube (and to really make @gateherder's day, find a copy of "Elements of Radio" and giving it a read!)_

_In the revolutionary triode vacuum tube, what is the name of the electrode that is used to control the flow of electrons from the cathode (heated by the filament) to the anode?_

Flag: **grid**

**Methodology**
If you go to the Wikipedia page for [Triodes](https://en.wikipedia.org/wiki/Triode), you can start searching pretty quick. Finding the answer can be as simple as guessing and checking all the components in the triode as shown on this graphic:

![220px-Triode-english-text svg](https://user-images.githubusercontent.com/85370905/134777174-122f4345-0605-4c59-b57f-005afd34fd30.png)

To be more precise, reading the actual page quickly shows that the _revolutionary_ difference between this vacuum tube and previous iterations is the inclusion of the control grid which should clue you in to the flag without guessing.

# EE101.6.2 - Vacuum Tubes
**Point Value:** 3

**Prompt**
_What part of the modern Field-effect transistor (FET) performs the same function as the triode's control grid?_

Flag: **gate**

**Methodology**
Start at the Wikipedia page for [FETs](https://en.wikipedia.org/wiki/Field-effect_transistor). Unfortunately _grid_ from the previous flag does not appear on the page, but you could still quicky guess and check the components on the image.

![FET_cross_section](https://user-images.githubusercontent.com/85370905/134777305-96d0a1af-122a-4ade-9b55-96524778a532.png)

Gate quickly stands out as the probable flag looking at the cross section of a FET, because it is in the center of the FET and would be the most likely component to moderate or control the flow of electrons.
