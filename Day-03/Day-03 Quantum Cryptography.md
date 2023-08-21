
Learning Objectives

Introduction to Stream Ciphers
Introduction to Block Ciphers
Random Number Generation(RNGs)
One Time Pad(OTP)
Linear Feedback shift register(LFSRs)

Introduction to Stream Ciphers

Stream Ciphers fall into the symmetric cryptographic algorithms which is invented in 1917 by Gilbert Verman. Stream ciphers encrypt bits individualy therefor there are works better for the smaller embedded devices which don't requires high level of security.

Encryption : $y_i = e_{si}(x_i) = x_i + s_i * mod \;2$

You can see here from the formula of encrytion is that it takes the input x with key and gives the our cipher text means it encrypt the data bit by bit individually. It is like the XOR gate transforms the bits.

Decryption : $x_i = e_{si}(y_i) = y_i + s_i * mod \; 2 \; where \; x_i, y_i, s_i \in \{0, 1\}$

Similarily cipher text and Key, what Alice Send to the Bob  it will be used as input to the decryption algorithm to decrypt the cipher text to retain the original message from Bob.

What is the difference between the Block Cipher and The Stream Cipher ?

> The main difference is that block cipher encrypt the block of bits while the stream cipher only encrypt the individual bit at a time. Block Ciphers are used to transfer large data over internet while Stream Ciphers are used to transfer smaller data like in GSM Phones.

What are the advantages and disadvantages of the stream ciphers ?

- It can work on smaller block sizes because it needs litle memory.
- When we try to randomly access it then it will be defficult for us and also we can't easly use the large key.

Introduction to Block Ciphers

> A symmetric–key block cipher encrypts n-bit block of plaintext into n-bit block of ciphertext using a key K. A message having more than n bits is divided into n-bit blocks and the last block having fewer than n bits is padded suitably to make n-bit block. Encryption and decryption are carried out taking one block at a time.

What are the advantages and disadvantages of the block cipher ?

What Shannon's Proposal is on the Cryptographically Secure system in 1945 ?

> He proposed two fundamental attributes called Confusion and Diffusion

- Confusion: In order to avert cryptanalytic attack on the cipher key, there should be a very complex relationship between the statistical characteristics of the ciphertext and the cipher key. A cryptographically secure system requires that changing even one bit of the cipher key should cause wide spread changes in the ciphertext.
- Diffusion: Diffusion refers to dispersing the statistical structure of plaintext so that it is not reflected in the statistical structure of the ciphertext. In the context of block cipher, it implies that changing one bit of n-bit plaintext block should cause wide spread changes in its n-bit ciphertext.

Random Number Generation(RNGs)

> there are there types of random number generator
> (1) True RNG
> (2) Pseudorandom RNG
> (3) Cryptographically Secure RNG

They used for generating random numbers for keys in encryption algorithms

One-Time Pad(OTP)

> One-time pad scheme of encryption is unbreakable. In case of one-time pad, the key used to encrypt and decrypt a message is as long as the message. It is chosen completely randomly from the key domain and is used to encrypt and decrypt a single message, after which it is discarded and is not used again. Thus, the key is also referred to as one-time pad. If the key is truly random, is at least as long as the plaintext, is never reused in whole or in part, and is kept completely secret, then the resulting ciphertext will be impossible to be broken. Clearly, the security of the one-time pad is entirely due to the randomness of the key because in this case ciphertext bears no statistical relationship with the plaintext which could be attacked by the cryptanalyst.

$$
c_i = p_i \; (Exclusive-XOR) \; k_i \; \\ where \; p_i = \; plane-text \\ k_i = i^{th} bit \; of \; key \\ c_i = i^{th} bit \; of \; cipher-text
$$

In theory One Time Pad in completely secure but it's practical implementation has two fundamental difficulty (1) problem of making large quantities of random keys (2) problem of key distribution and protection.

Linear Feedback Shift Register(LFSRs)
