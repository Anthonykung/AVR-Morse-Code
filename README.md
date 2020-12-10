# AVR-Morse-Code

## ANTHONIAN MORSE CODE ENCODING
---------------------------------
AVR registers are 8 bits

Morse Code for A to Z has a maximium of 4 "thing" (dot or dash)

That leaves 2 bits each for AVR register

So we can encode it as follow:

| Morse Code | 2-bits Code |
| ---------- | ----------- |
| Nothing    | 00		       |
| Dot .      | 10          |
| Dash -     | 11			     |
| Space	     | 01          |

*Correction: we don't even need space...*
*Correction: Dot changed from 01 to 10 for more efficient processing*

And for 1 character we can use one 8-bits register as follow:

**Note: crumb == 2-bits**

| CHAR | 1st Crumb | 2nd Crumb | 3rd Crumb | 4th Crumb |
| ---- | --------- | --------- | --------- | --------- |
| A    | 10		     | 11		     | 00		     | 00		     |
| B    | 11		     | 10		     | 10		     | 10		     |

Set up variables like this

```assembly
.equ	morseA = 0b10_11_00_00	; Morse code A using Anthonian Morse Code Encoding :P
.equ	morseB = 0b11_10_10_10	; Morse code B
.equ	morseC = 0b11_10_11_10	; Morse code C
.equ	morseD = 0b11_10_10_00	; Morse code D
.equ	morseE = 0b10_00_00_00	; Morse code E
.equ	morseF = 0b10_10_11_10	; Morse code F
.equ	morseG = 0b11_11_10_00	; Morse code G
.equ	morseH = 0b10_10_10_10	; Morse code H
.equ	morseI = 0b10_10_00_00	; Morse code I
.equ	morseJ = 0b10_11_11_11	; Morse code J
.equ	morseK = 0b11_10_11_00	; Morse code K
.equ	morseL = 0b10_11_10_10	; Morse code L
.equ	morseM = 0b11_11_00_00	; Morse code M
.equ	morseN = 0b11_10_00_00	; Morse code N
.equ	morseO = 0b11_11_11_00	; Morse code O
.equ	morseP = 0b10_11_11_10	; Morse code P
.equ	morseQ = 0b11_11_10_11	; Morse code Q
.equ	morseR = 0b10_11_10_00	; Morse code R
.equ	morseS = 0b10_10_10_00	; Morse code S
.equ	morseT = 0b11_00_00_00	; Morse code T
.equ	morseU = 0b10_10_11_00	; Morse code U
.equ	morseV = 0b10_10_10_11	; Morse code V
.equ	morseW = 0b10_11_11_00	; Morse code W
.equ	morseX = 0b11_10_10_11	; Morse code X
.equ	morseY = 0b11_10_11_11	; Morse code Y
.equ	morseZ = 0b11_11_10_10	; Morse code Z
```
