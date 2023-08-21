# Fiestel Cipher Structure, Data Encryption Standard(DES) and Advanced Encryption Standard(AES)

## Introduction

> Fiestel Cipher is developed by the Hoste Fiestel(Physicist) and he also contributed into the Data Encryption Standard(DES), later with few improvement it became Advanced Encryption Standard(AES). The Structure of DES is called fiestal cipher/network means it is not like an algorithm it gives the basic structure for the algorithms like DES and AES and Feeding Input along with key gives us the encrypted output.

> Encryption : We create a two way input(left and right boxes) one for message and another for the keys then we pass it to some kind of hash function and then reverse input and again pass it to another hash function it repeates until our (last step - 1) and to get the output we just revese it in the last round.

> Decryption : We don't needed to create new or even reverse our architecture because, how fiestel work is totally symmetrical in nature. We can use the same architecture for the decryption also, it don't depends on  our function has it's inverse or not.

## Fiestel Cipher Structure

> The inputs to the encryption algorithm are a plaintext block of length 2w bits and a key K. The plaintext is divided into two halves, L0 and R0. The two halves of the data pass through n rounds of processing and then combine to produce the ciphertext block. Each round i has Li-1 and Ri-1as inputs which are obtained as output of the previous round. Also, round i takes round key kias input where ki is derived or obtained from the overall key K.

> All rounds have the same structure. A substitution is performed on the left half of the data and right half of data remains unchanged. This is done by applying a round function f   to the right half of the data where the round key ki is also used as another input parameter to round function f. Then exclusive-OR of the output of the round function f   and the left half of the data is taken. This  becomes  the  substitution  value  for  the  left  half  of  the  data.  After  substitution,  a permutation is performed by interchanging the two halves of the data. So, the ith iteration of the encryption algorithm can be represented as: 

$$
L_i = R_{i-1} \\ R_i = L_{i-1} (Exclusive-XOR) F(R_{i-1}, K_i)
$$

> Once the last round is completed then the two halves Ln and Rn are again swapped to generate the ciphertext as a concatenation of the form R_n || L_n ,where || to represent concatenation. This last swapping makes the encryption and decryption algorithm same.

> The exact realization of a Feistel network depends on the choice of the following:
  - Block Size: Larger block sizes mean greater security but reduced encryption/decryption speed for a given algorithm. Block sizes of 64 bits and 128 bits are commonly used.
  - Key Size: Larger key size means greater security because of higher resistance against brute-force  attack  and  also  greater  confusion.  But,  this  may  decrease encryption/decryption  speed.  Key  sizes  of  64  bits  or  less  are  widely  considered inadequate now.
  - Number of rounds: The essence of the Feistel  Cipher is that  a single round offers inadequate security and that multiple rounds can offer higher security. So, appropriate number of rounds have to be decided while designing an encryption scheme so as to strike a balance between security offered and performance speed of the scheme.
  - Subkey  generation  algorithm:  Greater  complexity  in  this  algorithm  should  lead  to greater difficulty of cryptanalysis.
  - Round  Function:  Greater  complexity  of  round  function  generally  means  greater resistance against cryptanalysis.

> The process of decryption with a Feistel Cipher is essentially the same as the encryption process but the round keys ki (1≤ i ≤ round count) are used in the reverse order during decryption. Following figure 1 shows the encryption process using Feistel Cipher Structure:

## Data Encryption Standard(DES)

> Data Encryption Standard (DES) was published in 1975 and was adopted as standard in 1977 by NIST (National Institute of Standards and Technology). DES was broken in 1999, which resulted in NIST issuing a new directive that required organizations to use Triple DES. DES is a block cipher with block size of 64 bits and key size of 56 bits. It is based on Feistel cipher structure with 16 rounds of operations. Each of the 16 round keys k1, k2, ... k16 is 48 bits
long and is derived from the original 56-bit key K. The overall structure of DES consists of the following: 
  1. Initial Permutation
  2. Sixteen rounds of encryption operations based on Feistel cipher structure
  3. Swapping of two halves of the intermediate cipher text after 16 rounds (as in Feistel cipher structure)
  4. Final permutation (which is actually inverse of the initial permutation)

> Firstly, the 64-bit plaintext passes through an initial permutation (IP) that rearranges the bits to produce the permuted intermediate ciphertext. This is followed by a phase based on Feistel cipher structure consisting of 16 rounds of the same encryption round function. The round function involves both permutation and substitution. The output of the last round consists of the 64-bits that are a function of the input plaintext and the key K. The left and right halves of the output of the last round function are swapped to produce the pre-output. Finally, the pre-output is passed through a final permutation (IP-1) that is the inverse of the initial permutation, to produce the 64-bit ciphertext. DES has the exact structure of a Feistel Cipher with just the exception of additional initial and final permutations.


> Initial Permutation: The initial permutation and its inverse are defined by tables. The input to the permutation table is a 64-bit block with its bits numbered from 1 to 64. There are 64 entries in the permutation table which contain a fixed permutation of the numbers 1 to 64 indicating
the corresponding positions of the input bits in the output 64-bit block.


> Encryption Round Details: Each round of DES follows the Feistel structure i.e. the 64-bit input to the round is treated in two 32-bit halves and one of the two halves is substituted while theother is not, and this is followed by swapping of the two halves. To elaborate, the right 32-bit half along with the 48-bit round key are the inputs to the scrambling function g which involves
both substitution and permutation operations. The 32-bit output of the scrambling function g is then XORed with the left 32-bit half and this becomes the substitution value for the left half
while the right half remains unchanged. This is followed by swapping of the left and the right halves thereby completing one round of operations.

> Swapping: The two halves of the 64-bit block generated at the end of last round i.e. round 16 are swapped (as done in Feistel Cipher Structure). Final Permutation: The 64-bit output obtained after swapping is subjected to final permutation which is inverse of initial permutation (IP-1). Note that at the time of decryption, the initial permutation restores the bits of the encrypted block to their original places thereby reversing the effect of Final Permutation. The decryption algorithm is exactly same as the encryption algorithm except that the round keys are used in the reverse order while performing decryption.

## Conclusion 
> We learned about the Fiestel Cipher Structure which is used in many algorithms like Data Encryption Standard's Version like 3DES, 5DES, 16DES etc. Next Day we learn about the Advanced Encryption Standard(AES). For more such articles follow me one medium blogs and on Linkedin.