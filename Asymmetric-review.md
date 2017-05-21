# Asymmetric cryptographic systems

## Shared Key Systems: 

* Both sender and receiver use the same key which must remain private.(symmetric). For example : DES,3DES..
* Problems:
	* compromised key means interceptors can decrypt any ciphertext.(solution: can be changed frequently)
	* Distribution of keys is problematic: keys must be transmitted securely.(solution: distribute key in piece over seperate channels)

## Public key System

* (asymmetric key system)Each user has a pair of key. (public and private key)
	* Public is used for encryption, key is known to public
	* private is used for decryption 
* Trapdoor Function(TDF)
	* construct a pair of function f,f^(-1)
	* given x, f(x)is trivial (不重要的)
	* given f and y, evaluation of f^(-1)(y)difficult(回退不容易)
	* given f^(-1) and y evaluation of f^(-1)(y) easy（给定回退方法，回退就容易）
	* A trapdoor function X->Y is a triple of efficient algorithms(G,F,F^(-1))
		* key generation algorithm(G): randomized algorithm outputs a key pair (pk,sk)
		* an encryption function (pk,*): determinisitic algorithm defines a function X-> Y
		* a decryption function F-1(sk,* ) Y->X inverts F(pk.*)
		* F^(-1)(sk,F(pk,x ))=x
	* secure TDF
		* if F(PK,*) is a one way function. cannot be inverted without sk 
		* if a adversary has C, pk, F. He could try to find function F-1 and apply it on the cipher. A(C,F,pk) -> p`
		* if it is secure TDF if for all efficient A: Adv(A,F) = Pr[p=p`] < negligible
		* <mark> Never encrypt by applying F directly to pt </mark>
		* Not semantically secure

## RSA as TDF Function

### Basic Key Generation Algorithm

*  Choose random primes p,q
*  set N=p.q
*  Choose Integer e d, e.d =1 mod 𝝋(N)
*  pk = (N,e), sk=(p,q,d)
*  Encryption Algorithm: RSA(x,e) = x^e
*  Decryption Algorithm: RSA(Y,D) = Y^d
*  <mark>y^d=x</mark>
*  M^e mod N = C 	C^d mod N = M

## RSA security

* RSA security depends on the fact that it is so far very difficult to factorize large integers
* Fermat number is a positive integer of the form 
	* F= 2^(2^(i))+1
	* F11 have been factorized
	*  Current RSA-768 (232 digits) --- 2 years and 100s of machine
* a run time of order: e^(O(N ^1/3))

## Textbook RSA

Encrypt: c: m^e  
Decrypt: m: c^d

## In Practice

* example: Rsa-2048 bits encryption of 128 bits AES private key  
128 bits private aes private key--preprocessing--> 2048bits ---RSA----> encrypted key session
* PKCS1
* 16bits+randompad+ff+msg=2048bits  
Resulting value is RSA encrypted 

## Attack

### Timing Attacks
* the time it takes to compute y^d mod N could expose d 
* countermeasures are based on masking the times taken by operations 

### Power Attacks 
* exploits the variation of power consumption of a cipher hardware under different input values to infer the key. For example , the power consumption of a smartcard while it is computed c^d mod N can expose d
*  

























 