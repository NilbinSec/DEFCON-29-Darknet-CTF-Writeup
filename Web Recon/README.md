# Web Recon Flags

Web Recon was a difficult section for many members of Nilbin Sec; it is a section of OSINT we have been rapidly progressing on over the past several CTFs. While we found some of the flags there were many more we may look to solve and add here over the coming year.

# Recon 01/20
**Point Value:** 8

**Prompt**
_Reconnaissance is an important first step in identifying attack surface of any target. There are a variety of things you can do to recon, at its core, this is just looking around, but it does help to know what common things are left around that could be requested, or abused, by an attacker. The answer to this is a RECON-01-XXXXXXXX code._

_Recon https://mail.themadhatters.xyz/_

Flag: **RECON-01-YDJTCGPE**

**Methodology**
Opening the page source for the mail server and Ctrl-F for 'recon' quickly found a comment for the first flag.

# Recon 02/20
**Point Value:** 8

**Prompt**
_Reconnaissance is an important first step in identifying attack surface of any target. There are a variety of things you can do to recon, at its core, this is just looking around, but it does help to know what common things are left around that could be requested, or abused, by an attacker. The answer to this is a RECON-02-XXXXXXXX code._

_Recon https://mail.themadhatters.xyz/_

Flag: **RECON-02-AJNBEPVB**

**Methodology**
Found via Inspect -> POST response headers

# Recon 03/20
**Point Value:** 8

**Prompt**
_Reconnaissance is an important first step in identifying attack surface of any target. There are a variety of things you can do to recon, at its core, this is just looking around, but it does help to know what common things are left around that could be requested, or abused, by an attacker. The answer to this is a RECON-03-XXXXXXXX code._

_Recon https://mail.themadhatters.xyz/_

Flag: **RECON-03-AJMLFXJD**

**Methodology**
Inspect Page under Applications, the flag is in the password field for the Cookies tab.

# Recon 04/20
**Point Value:** 8

**Prompt**
_Reconnaissance is an important first step in identifying attack surface of any target. There are a variety of things you can do to recon, at its core, this is just looking around, but it does help to know what common things are left around that could be requested, or abused, by an attacker. The answer to this is a RECON-04-XXXXXXXX code._

_Recon https://mail.themadhatters.xyz/_

Flag: **RECON-04-MCUVYEWD**

**Methodology**Inspecting the page there is an asset in java script with the following interesting snippet:
_Konami\x20Code?\x20Darknet\x20recon\x20code?\x20I\x27m\x20Confused.\x20Here,\x20take\x20this:\x20\x52\x45\x43\x4f\x4e\x2d\x30\x34\x2d\x4d\x43\x55\x56\x59\x45\x57\x44_
While it appears there is some automated process to decipher this, just breaking out hex to ASCII does it.
