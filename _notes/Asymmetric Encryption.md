---
aliases:
  - Public Key Encryption
tags:
  - published
---
Asymmetric Encryption, also known as public-key cryptography, is a method used for encrypted exchange. Each partner in the exchange has a private key and a public key that are mathematically linked via methods such as [[RSA Encryption]], but cannot be derived from one another. A message encrypted with the public key can only be decrypted by the corresponding private key. 

When partner A wants to send a message to partner B, partner B first shares their public key with A. A then uses this public key to encrypt a sensitive message, then sends it to B to be decrypted using their corresponding private key. [(1)](https://www.youtube.com/watch?v=AQDCe585Lnc)

Asymmetric encryption can be understood using the metaphor of a locked ballot box. Each participant has their own locked ballot box (public key) and a corresponding key to open it (private key). To exchange messages, the locked ballot box is given to another participant, filled with their messages, then returned to recipient to be unlocked. 

Asymmetric cryptographic systems are often used to safely exchange a key and establish a communication using [[Symmetric Encryption]], which is more efficient. 