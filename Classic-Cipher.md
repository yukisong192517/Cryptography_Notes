# Classic Cipher

## compression and encryption

both are manipulating information

### Compression

extract information from the data, encode as efficiently as possible, public algorithm

### Encryption

Diffuse(扩散) a key into the information 


### Combination

transmit secure data: compress the data(reduce cryptanalysis on redundancy on the data)--> encrypt (compression pipeline information into flow, decrease the volume of data into encryption system)---> add error detection and recovery

### important word


| Term | Description 				|
|:-----|:-----------------------:|
| PT   |   message in clear form |
| Steganography |conceals the existences of the message |
| Cryptography| message in plain view, but meaning is concealed |

## Classic Cipher

### Caesar Cipher

* through frequency analysis: AEIOU is high frequency
* pairs of letter :vowel
* reversed diagrams: vowel

### Polyalphabetic Ciphers

同一个字母有的换，有的不换

### Vigenere Cipher

* Basic Approach:
	* find key length
	* divide the message into simple substitution encryption
	* frequency analysis 
	* how to find key:
		* Kasisky Test
			* search pair of identical segment (l>=3)
			* record distance between them
			* m should devide the gcd(distances)
		
		* Index of Coincidence
			* defined the probability that two randomly selected letters from a text will be identical
			* Ic= 𝚺f(f-1)/N(N-1)(for normal English:0.066)
			* Friedman:  
			make a guess of key lenth---> arrange text into matrix---> calculate IC for y-ym
			
### Roter Cipher Machine

### Transposition Cipher

### Rail Fence Cipher

### Columnar Cipher

* 竖着写
* 重新排列

## Steganography

*  secret writing
*  cryptography: although encrypted and unreadable, the existence of data is not hidden
*  Steganography: no knowledge of the existence of the data
*  method:
	*  tatto message on the head
	*  invisible sink. wrote on silk, crunched into a small ball, covered in wax. messenger swallow the ball of wax
	*  microdots: shrinking a page of text into dot,hide the microdot in an letter.
	*  null cipher : hide in the sound message
*  Visual steganography: hide message in an image

## Hybrid Cryptosystems

