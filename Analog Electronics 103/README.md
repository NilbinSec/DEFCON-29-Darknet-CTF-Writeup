# Analog Electronics 103

The final analog electronics section really amps up the difficulty in places. Solving these flags was really satisfying and felt like the real challenge of this section at times.

# EE103 with Gateherder
**Point Value:** 0

**Prompt**
_Fantastic work, agent! @gateherder may have a need for someone with your skills, but don't smile too soon! First you'll need to prove your worth with these final real-world scenarios.. If you successfully complete this quest, @gateherder will certainly be interested in hearing from you!_

_Let's start the next section. Enter prove my worth in the daemon_

Flag: **prove my worth**

**Methodology**
The first flag is just a gatekeeper to unlocking this set of challenges

# EE103.1 - Divide and Conquer
**Point Value:** 7

**Prompt**
_A common electronic circuit is a voltage divider network, which can be used when you need to cut down the voltage from one circuit before feeding it into another. This can be done in many ways, but the easiest is often a resistor divider network; if your input and desired output voltages (and currents!!) are always known (e.g. stepping down from a 5VDC source signal into a 3.3VDC receiving device)._

_More information can be found at: https://en.wikipedia.org/wiki/Voltage_divider._

_In the circuit found at https://bit.ly/32H9RAj, Vin=5Vdc, R1=6k-ohm, R2=12k-ohm. How many volts appear at the point labeled Vout? (e.g. "15.0VDC")_

Flag: **3.3VDC**

**Methodology**

**Methodology pending release of the bitly link**

# EE103.2 - Fools Inrush
**Point Value:** 7

**Prompt**
_Turning on an electrical circuit is like starting your car -- it’s the time when the circuits are strained the most. Capacitors aren’t yet charged, motors aren’t yet spinning; it takes much more energy to start it all up than it does to keep it going. This “start-up energy” is also known as “inrush current.”_

_Remember the capacitor? The industry standard time it takes to “charge a cap” is 5T (or 5 * Tau). At T=0, when the circuit is first activated, the capacitor is completely empty. Remember Ohm’s Law? It says that I = V/R (Current equals Voltage divided by Resistance). Now also consider that for most circuits, we want unnecessary resistance to be minimized so that we’re not wasting power. But if that “R” value in Ohm’s Law (when solving for current) is small, the resulting current can be huge!_

_A real (e.g. non-ideal) capacitor has a capacity of 12 uF, and has a parasitic resistance (called its Effective Series Resistance, or ESR) of 8 milli-Ohms. If the capacitor is completely discharged when 5VDC is applied to it to charge it, how high could the peak inrush current theoretically be when the circuit is activated (e.g. “10A”)?_

Flag: **625A**

**Methodology**
This prompt is overloaded with information; it is a red herring. At T = 0  capacity of the capacitor with a small capacitor does not matter. You should just divide voltage by resistance or: 5 / 0.008 which = 625 providing the flag.

# EE103.3.1 - One Ring to Rule Them All
**Point Value:** 7

**Prompt**
_Long before there were digital electronics, there were ring oscillators. Ring oscillators are similar to software's “hello world”, and are still in wide use today. They are used to verify quality at the wafer level for even the most expensive Intel processors. They are used in NIST-approved cryptographic hardware random number generators. They are embedded into the streets of most traffic-light intersections. They are the fundamental backbone to the tunable AM/FM radio. Ring oscillators are the precursor to digital, square-wave oscillators which enable all modern digital electronics. They can be built with digital gates or analog transistors. They can be tuned with RC time constants (and many other methods). Their application extend into optics, metal detectors, and even lasers!_

_For more information, check out https://en.wikipedia.org/wiki/Ring_oscillator._

_What discrete component is commonly used to build a ring oscillator by connecting an odd number of them in a series/chain, with the output from the last one feeding back around as the input to the first one?_

Flag: **inverter**

**Methodology**
Going to the Wikipedia link provided you can learn that Ring Oscillators are made up of NOT gates which are also known as inverters which provides the flag.

# EE103.3.2 - One Ring to Rule Them All
**Point Value:** 7

**Prompt**
_Using seven ideal inverters, each with a delay of 72.8862ns, you could construct a ring oscillator to provide the base carrier frequency of what local radio station near Reno, NV?_

Flag: **KVLV**

**Methodology**
Sure we could just google for radio stations around Reno, NV and start guess and checking, but that is no fun. The Wikipedia page from the previous flag gives this formula:

![image](https://user-images.githubusercontent.com/85370905/134780534-b79e81f9-d18d-40f5-9029-9459cff43b19.png)

So we need to calculate 1 / ( 2 * 7.28862e-8 * 7 ). This results in 980,001.3092817492 which can be simplified to 980KHz. A little bit of OSINT digging shows that 980KHz is the frequency for KVLV out of Fallon, NV which is near to Reno.

# EE103.4 - The Incredible (non-edible) Transistor
**Point Value:** 7

**Prompt**
_The invention of the transistor catapulted the modern electronics age. Smaller and (much) less power hungry than a vacuum tube, transistors could be packed into a smaller space, enabling rapid shrinking of electronics and ultimately the creation of the integrated circuit that is powering the device you're using at this very moment! Like vacuum tubes, transistors can be used as on/off switches, or as signal amplifiers. They can be combined into darlington arrays, used as the control system in switched-mode power supplies, grouped together to retain information in flip-flops and RAMs, and combined to construct an entire arithmetic logic unit (ALU), the fundamental building block of a modern computer processor. For more information, start here: https://en.wikipedia.org/wiki/Transistor._

_Two BJT NPN transistors are connected in the form of a darlington array in order to turn on and off a 25V, 100W lamp. The forward current gain of the first BJT (β1) is 30 and the second (β2) is 50. Ignoring any voltage drops across the two transistors (e.g. assume ideal transistors), what is the base current (B), in Amperes, required to switch the lamp fully ON? (round answer to the nearest half milliamp) Use the following image as a reference: https://goo.gl/aH5qnC._

Flag: **2.5mA**

**Methodology**

The goo.gl link is currently unavailable but this can still be solved with the given information. First a good example formula pulled from the internet:

![image](https://user-images.githubusercontent.com/85370905/135189920-cf45c713-312a-4838-8611-66e0df83d602.png)

Applying our numbers, I = 100 Watts / 25 Volts = 4 Amps at the lamp. To calculate gain from the array we use the final equation:

4 Amps / (30 + (30x50) + 50) = 0.0025316... = 2.5mA our flag

# EE103.5.1 - The Many Faces of Dr. Opamp
**Point Value:** 7

**Prompt**
_Op-amps (or operational amplifiers) are everywhere. They are extremely versatile. They can be used to increase/boost the strength of a signal, or reduce/attenuate an incoming signal to protect other more sensitive circuits downstream. They can mix multiple signals together, or be used to split them apart. They can compare incoming signals and raise alarm flags when an incoming signal is too strong or too weak. They can be used to filter out parts of an incoming signal that are not desirable._

_It is often useful to simulate opamp circuits before building them to get a rough ballpark figure of operation. Due to non-ideal components, many times tuning the circuit after production is necessary. But a simulation ahead of time can reduce the frustration significantly. There are many simulation tools available. See https://en.wikipedia.org/wiki/Electronic_circuit_simulation for a non-exhaustive list._

_For each question below, reload a fresh copy of the circuit at http://everycircuit.com/circuit/4735544197382144/ramping-signal-generator-._

_What is the frequency of the voltage oscillation seen across the capacitor? (e.g. "10Hz")_

Flag: **326kHz**

**Methodology**
Start by loading the circuit in the prompt. After letting the current run through the entire circuit and reach equilibrium, you can select the capacitor and see the correct answer listed at the top under Frequency:

![image](https://user-images.githubusercontent.com/85370905/134780784-b3caa9a1-e7fa-4223-b48e-262b5cb59d10.png)

 # EE103.5.2 - The Many Faces of Dr. Opamp
**Point Value:** 7

**Prompt**
_What is the closest standard value capacitor (in picofarads) needed to achieve a frequency of approx 190 kHz? (e.g. "10pF")_

Flag: **800pF**

**Methodology**
Increasing capacity of the capacitor will lower the frequency of the circuit. Because this simulator allows new inputs on the fly, you can guess and check for yourself. A frequency of 190kHz is acheieved around 801-803pF depending on how the simulator is feeling. Because the prompt asks for a standard value capacitor we can test 800pF and get the flag, but... during research it looks like the actual flag should be 820pF which is a more commonly available capacitor value.

 # EE103.5.3 - The Many Faces of Dr. Opamp
**Point Value:** 7

**Prompt**
_What maximum voltage is achieved across the capacitor when the resistor connected to the inverting input of the opamp is dropped an entire magnitude from 10kOhm to 1kOhm? (round to the nearest tenth of a volt, e.g. "5.2V")_

Flag: **10.4v**

**Methodology**
When solving this problem, it was not immediately clear which was the inverting input of the opamp, but the prompt does say 10kOhm and there are four 10kOHm resistors in the circuit so we can start testing each for the flag. Modifying most break the circuit very quickly, but the lower right resistor when modified to 1kOhm returns the flag once the current has passed through the entire circuit.

![image](https://user-images.githubusercontent.com/85370905/134781193-697baacf-1730-45be-a7eb-e77dc3e43a5c.png)
