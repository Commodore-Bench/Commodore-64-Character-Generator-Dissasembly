# Commodore 64 character generator
The commodore 64 is one of the most infamous computers in the history. It has 3 main chips which containin information. The **Kernal** chip, the **Basic** chip and the **Character Genrerator** chip. The source code of the Kernal and Basic can be found in [Steve Gray's Website](http://6502.org/users/sjgray/dj/). But what about the character generator source code? Well, I've been looking for it during some time, but I wasn't able to find it, so I opened my old thustworthy hex editor and looked at the chip dump I had in my computer and started writing a simple assembly file compused by "db"'s. At first it was the raw hex, but recently I have comberted it to binary.

## About Character Generator ROM
### What does ROM mean?
Rom stands for Read Only Memory and unlike the RAM (Random Access memory) it cannot be written to.
### Does it really generate characters?
No, I don't know why it's named character generator because it just contains the character set.
### The chip itself
The chip the commodore 64 used is a MOS 901225-01

## About the characters
### Characters
The characters in the commodore 64 are pixels in a 8x8(64 what a coincidence!) grid in which the pixels can be of two colors: The background color(Represented by a 0) and the foreground color(Represented by a 1).
### Let's Talk about numbers
Each character occupies 8 bytes.

There are 512 characters separed in two charactersets(Uppercase & Lowercase) of 256 characters which are separed in 128 charactersets (Normal & inverted) (You can see them below).

The total filesize of the rom is 4096 bytes.

## Character images
![Commodore 64 Upper charset](http://www.coding64.org/wp-content/uploads/2014/10/c64_upp.gif)

![Commodore 64 Lower charset](http://www.coding64.org/wp-content/uploads/2014/10/c64_low.gif)
## About this repository
### Files
I have included the original character generator rom as "orgcg.bin".

The code itself is in "chargen.asm"(NOTE: It has the CRLF format).

I have made a quick & dirty character editor in html which includes some superbasic functions to load characters. Use updateRow("value", "type(dec, hex or bin)", "row number") or updateTable("type(dec, hex or bin)", "value 1", "value 2", "value 3", "value 4", "value 5", "value 6", "value 7", "value 8") on the JavaScript console to load the characters.

The special letter's meaning in "chargen.asm" cna be found in "special.txt".
### Chargen.asm
The structure of the file is very simple:

db(Define Byte) binary_data;Represented Character

This line 7 more times

[Return]

And repeat

The Represented Character portion is written in ANSI and some especial case there's a Unicoide character inserted (If you can't see unicoide characters in your editor I've added a little description at it's side).

### Assembling
In theory any Assembler can assemble the source code if they suport the define byte instruction, the binary data type and commentaries.
For example I used the [Netwide Assembler](https://www.nasm.us/) myself with the commandline "nasm -fbin -ochargen.bin chargen.asm"

### Contributing
Well, there's nothing stopping you from making a pull request.

If you feel that there's a better symbol for representing the commodore 64 character or you've noticed that I have done a mistake feel free to make one.

## Webgraphy
[Coding 64](http://www.coding64.org/)

[Netwide Assembler](https://www.nasm.us/)

[Steve Gray's Website](http://6502.org/users/sjgray/dj/)
