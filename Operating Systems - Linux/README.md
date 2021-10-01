# Operating System - Linux Flags

This was probably one of the easiest sections, the primary goal was to search through a free book on Kali Linux. Starting off, here is a [Link](https://kali.training/downloads/Kali-Linux-Revealed-2021-edition.pdf) to the book that is used

# Kali Intro - Part 1
**Point Value:** 5

**Prompt**
_So you have come here to learn about Kali Linux. Back in my day, things where not so simple... But this is the information age, so lets jump right in._

_Things could not be simpler. I am going to give you reference material that you will want to download and keep accessible._

_Go to https://kali.training/ and download the PDF of Kali Linux Revealed Book._

_In the "Mastering the Penetration Testing Distribution (2021)" version, What is the first line in the preface of the book?_

Flag: **You have no idea how good you have it.**

**Methodology**
As was stated in the introduction, downloading the book was all that was required for this flag, the answer is on page 14 of the pdf, the first page of the preface.

# Kali Intro - Part 2
**Point Value:** 5

**Prompt**
_Kali Linux has not been built to be a simple collection of tools, but rather a (2 blanks) that professional penetration testers, security enthusiasts, students, and amateurs can customize to fit their specific needs. Fill in the blanks from the above paragraph._

Flag: **flexible framework**

**Methodology**
Flag is in the introduction on page 22, just a bit of Ctr-F.

# Kali Intro - Part 3
**Point Value:** 5

**Prompt**
_Desktop Environments can change the way your Linux desktop looks. You can make it look like Old XP, Windows 7 with Gadgets, OSX, or the Shield OS from the Avengers, or create your own unique look and feel._

_According to the Kali-Linux-Revealed-2021-edition, XFCE is the default. They have a list of 7 other options. What is the last Desktop Environment on that list?_

Flag: **LXDE**

**Methodology**
More Ctr-F, flag is on page 30 of the pdf.

# Kali Intro - Part 4
**Point Value:** 5

**Prompt**
_A Linux distribution (often abbreviated as distro) is an operating system made from a software collection, which is based upon the Linux kernel, and often a package management system._

_There are Large families of distros. Check out this wiki to see just how many there are. https://en.wikipedia.org/wiki/List_of_Linux_distributions_

_Linux users usually obtain their operating system by downloading one of the Linux distributions, which are available for a wide variety of systems ranging from embedded devices and personal computers to powerful supercomputers._

_According to the Kali Linux Revealed book, what distro is Kali based on?_

Flag: **Debian Testing**

**Methodology**
This flag was a bit more difficult to find, as the first thought is to look at the history of kali section which rattles off a long list of different iterations of Kali and its history. After exhausting some of the other options the correct answer delivered the flag.

# Kali Intro - Part 5
**Point Value:** 5

**Prompt**
_Once you have booted, and click the Kali Linux’s Applications Menu you'll find that is organized._

_According to the book, what is the 6th number of tasks and activities listed?_

Flag: **Wireless Attacks**

**Methodology**
Little bit of Ctr-F and searching, flag is on page 34 of the pdf.

# Kali Intro - Part 6
**Point Value:** 5

**Prompt**
_A live medium (cd, dvd, or thumb drive) is a complete bootable computer installation including operating system which runs in a computer's memory, rather than loading from an internal hard disk drive; the live medium itself is read-only._

_It allows users to run an operating system for any purpose without installing it or making any changes to the computer's configuration._

_Live medium can run on a comptuer without secondary storage, such as a hard disk drive, or with a corrupted hard disk drive or file system, allowing data recovery._

_You can add the ability to save your changes, by enabling persistence mode. On what page number from the book can you learn how to do this?_

Flag: **246**

**Methodology**
Nothing really good to search for, instead turning to the Table of Contents finds the flag pretty qucikly (Note: The page number in this case is the book page number, not the pdf page number)

# Kali Intro - Part 7
**Point Value:** 5

**Prompt**
_In addition to Live and Persistence, there is another mode you can use. Forensics is for when you want to avoid any activity that would alter the data on the analyzed system in any way._

_Modern desktop environments tend to "help the user" by trying to BLANK any disk(s) they detect._

_What does the Forensics mode disable by default, fill out the 2 blanks above._

Flag: **auto-mount**

**Methodology**
Ctr-F for forensics mode quickly found the flag on page 35 of the pdf.

# Kali Intro - Part 8
**Point Value:** 5

**Prompt**
_Many of the tools bundled in Kali need root access to run, so by default that is the only account used from the start. This is NOT COMMON BEST PRACTICE and can lead to destructive mistakes._

_Since this distro is used for security and recon, it needs to be as quiet as possible, so it disables services out of the gate. This way you can decide when or if you want to use them._

_In contrast to Debian, Kali Linux disables any installed service that would listen on a public network interface by default, such as HTTP and SSH. On what page number can you learn how to turn Apache on?_

Flag: **118**

**Methodology**
Ctr-F for Apache and using context found the flag.

# Kali Intro - Part 9
**Point Value:** 5

**Prompt**
_Unlike most mainstream operating systems, Kali Linux is a BLANK distribution, which means that you will receive updates every single day._

_What type of distro is kali, fill in the blank from above._

Flag: **rolling**

**Methodology**
Honestly, this flag was a lucky guess based on knowledge of Kali.

# Kali Linux 101
**Point Value:** 5

**Prompt**
_The only official source of Kali Linux ISO images is the Downloads section of the Kali website._

_Due to its popularity, numerous sites offer Kali images for download, but they should not be considered trustworthy and indeed may be infected with malware or otherwise cause irreparable damage to your system._

_According to the Kali Linux Revealed free ebook, what is the correct website to download the ISOs from?_

Flag: **https://www.kali.org/downloads/**

**Methodology**
This was a great question because the Kali website actually redirects to a different page. The answer is on page 41 of the PDF and was found by looking at the Table of Contents.
