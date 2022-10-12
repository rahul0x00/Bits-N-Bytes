# Some Malware Analysis Terminology

### Packer/Packed

Packer sometimes referred to as Crypted

A packer or crypter takes an executable or DLL and compresses or encrypts or deobfuscates it

And it's stored in *Stub*,the Stub contains the unpacking mechanism and acts as a loader for packed file,Stub typically performs some type of injection like DLL Injection, Process Hollowing,etc to run executable under other process,making the detection much harder.

### Obfuscation

Obfuscation is the obscuring of the intended meaning of program by making the code difficult to understand, usually with confusing and ambiguous ...
It's main goal is to make the analysis slow down.

### Disassembler

It allows us understand the execution of a file before running it, it's knows as static analysis 

### Debugger

### IOCs

Indicators of Compromise-This directory is used to determine whether you're compromised by this sample or not.

It contains the information of the file such as 
	File Hashes
	File names
	Email Address
	Modified Register Keys,etc
 



