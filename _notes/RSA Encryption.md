---
tags:
  - published
---
RSA is an algorithm used for [[Asymmetric Encryption]] where each partner has private key and a public key that are mathematically linked, but cannot be derived from one another. A message encrypted with the public key can only be decrypted by the corresponding private key. 

## Key Generation

The [[Algorithm]] for generating a key-pair via RSA is as follows:

1. Select two prime numbers, $p$ and $q$
2. Calculate $n=p \times q$ 
3. Calculate $\phi(n) = (p-1) \times (q-1)$ 
4. Choose encryption exponent $e$ such that
	- $1<e<\phi(n)$
	- $e$ is [[Coprime]] with $\phi(n)$
5. Calculate decryption exponent $d$ such that
	- $d \times e = 1 \text{mod} \phi(n)$
	- (It’s not too complicated, just fill in the values!)
6. The resulting factors of $n$, $e$, and $d$ are used as input to the below functions.

## Encryption

$C=M^e\text{mod}n$, where $C$ is cipher text and $M$ is the original message, converted to numerical representation via [[ASCII]] or another encoding scheme, and $e$ and $n$ are parts of the public key.

## Decryption

$M=C^d\text{mod}n$, where $M$ is the original message, and $d$ and $n$ are parts of the private key. The decryption exponent $d$ must be kept private, as it is used to decrypt the message. 