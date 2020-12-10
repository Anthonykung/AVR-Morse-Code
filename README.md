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
| Dot .      | 01          |
| Dash -     | 11			     |
| Space	     | 10          |

*Correction: we don't even need space...*

And for 1 character we can use one 8-bits register as follow:

**Note: crumb == 2-bits**

| CHAR | 1st Crumb | 2nd Crumb | 3rd Crumb | 4th Crumb |
| ---- | --------- | --------- | --------- | --------- |
| A    | 01		     | 11		     | 00		     | 00		     |
| B    | 11		     | 01		     | 01		     | 01		     |
