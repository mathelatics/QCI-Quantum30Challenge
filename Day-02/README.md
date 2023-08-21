# Day-02 Quantum Cryptography - Modular Arithmetics and Historical Encription Algorithms

**Learning Objectives**

- Modular Arithmetics
- Rings & Fields from Ring and Field Theory
- Shift Cipher
- Affine Cipher

## 1. Modular Arithmetics

Goal : Computation in a Finite sets.

- Examples of finite sets in every day life ? Think about it. [Clock for time : 0-24 and circular i.e <!-- $y = x * mod(24)$ --> <img style="transform: translateY(0.1em); background: white;" src="https://render.githubusercontent.com/render/math?math=y%20%3D%20x%20*%20mod(24)"> it is the remainder operator(modular operator) ]

Definition of Modular Operator :

> *Let <!-- $a, r \in\mathbb{Z}$ --> <img style="transform: translateY(0.1em); background: white;" src="https://render.githubusercontent.com/render/math?math=a%2C%20r%20%5Cin%5Cmathbb%7BZ%7D"> and <!-- $m \ge 0$ --> <img style="transform: translateY(0.1em); background: white;" src="https://render.githubusercontent.com/render/math?math=m%20%5Cge%200"> then we can write  <!-- $ a \equiv r * mod(m) \; \forall \; m \in\mathbb{Z}$ --> <img style="transform: translateY(0.1em); background: white;" src="https://render.githubusercontent.com/render/math?math=a%20%5Cequiv%20r%20*%20mod(m)%20%5C%3B%20%5Cforall%20%5C%3B%20m%20%5Cin%5Cmathbb%7BZ%7D">* if m divides <!-- $a-r \;i.e \; m | (a-r)$ --> <img style="transform: translateY(0.1em); background: white;" src="https://render.githubusercontent.com/render/math?math=a-r%20%5C%3Bi.e%20%5C%3B%20m%20%7C%20(a-r)">.

- Example-1 : a = 15 and m = 7 the find r using <!-- $15 = r * mod(7)$ --> <img style="transform: translateY(0.1em); background: white;" src="https://render.githubusercontent.com/render/math?math=15%20%3D%20r%20*%20mod(7)"> i.e equal to 1.
- Example-2 : <!-- $a = 13 \; and \; m = 9 \; then \; t = ? \implies 13 \equiv t * mod(9)$ --> <img style="transform: translateY(0.1em); background: white;" src="https://render.githubusercontent.com/render/math?math=a%20%3D%2013%20%5C%3B%20and%20%5C%3B%20m%20%3D%209%20%5C%3B%20then%20%5C%3B%20t%20%3D%20%3F%20%5Cimplies%2013%20%5Cequiv%20t%20*%20mod(9)">, gives t = 4.

Computation of Remainder(Division Algorithm) :

> Given <!-- $a, m \in \mathbb{Z} \; then \; a = q*m + r$ --> <img style="transform: translateY(0.1em); background: white;" src="https://render.githubusercontent.com/render/math?math=a%2C%20m%20%5Cin%20%5Cmathbb%7BZ%7D%20%5C%3B%20then%20%5C%3B%20a%20%3D%20q*m%20%2B%20r"> q is the quotients and r is the remainder

- Example-1 : a = 49 , m = 8 then compute r = ? (1 or -7)

Note : Remainders are not unique.

Equivalence Classes :

- Example-1 : a = {12, 13} and m = 5 then r = {[2, -3], [3, -2]} but we construct set of remainder i.e { ... , - 8, -3, 2, 7, 17, ...} all forms an equivalence class modulus 5.  All members of the class behave equivalent to modulus 5.

## 2. Rings and Fields

## 3. Shift Cipher
it is based on the modular arithmetic. Every text of english word consists of the 26 alphabets. <!-- $$c = m + k * (mod 26)$$ --> 

<div align="center"><img style="background: white;" src="https://render.githubusercontent.com/render/math?math="></div>

It has two components one is for algorithm which shift characters by a fixed amount and Key which is a fixed value.

Example : Caesar Cipher : Let k = 3 and then c = m + 3 * (mod 26). means each m-th character will be replaced with (m + 3)-th character.

Planetext : Attack at dawn
Ciphertext : Dwwdfn dw gdzq

It is easy to creack because even if we don't know about the key and we know the algorithm then there are only 25 possibilities to crack it using brute force attack. but there is an easy method that is the frequency analysis of each alphabet.

## 4. Affine Cipher
It is also based on the modular arithmetic thus it's formula are <!-- $$c = (am + b) * mod \; 26 \\ m = a^{-1}(c - b) * mod \; 26$$ --> 

<div align="center"><img style="background: white;" src="https://render.githubusercontent.com/render/math?math="></div> where a and b are the key parameters.

Problem with such encription is that they can be easly brocken because there exits a linear relationship between the message and the corresponding cipher using frequency analysis of each letters we can easly crack it.


## Quantum Tools and Quantum Key Distribution Protocol

> We already learned about the quantum information concepts like quantum states : pure, mixed states, quantum entanglement, quantum measurement, reduced states and many more. Then Here we are going to think about the question i.e What are the use of quantum information into the study of quantum cryptography like intutive idea and notations. We also learn about the first quantum cryptographic scheme called one time pad which allows the perfectly secure encryption of quantum states using classical key, it is anologouse to the classical one time pad cryptographic protocol.

What is the Quantum Cryptography ?

> The goal of quantum cryptography is how can we perform quantum communication to achieve information security.

Quantum Key Distribution(QKD) :

- Entities : Alice and Bob
- Task : Communication of massages like Alice want to send some massage or pictures or even files to the Bob.
- Easedroper(Adversory) : Ajeet try to listen Alice and Bob communication
- Communication Channels : Air, Wire etc can be intercepted by Easedroper
- How can Alice and Bob privent Ajeet from listening their massages. How Alice and Bob should communicate. Why we needed to protect our information.
- Cryptography provides a shafe box called encryption which can encrypt massages inside the box and lock the box with certain key. Then Alice send encrypted messege box to Bob and Bob has a copy of the same key to open that box to get the secret massege. Our box will be safe until easedroper don't have the box key. So, Our information is secure now, but How much key we needed to protect our messages
- Shannon has proved that in order to achieve absolute security we needed a key space as long as our massages which is a huge amount of key itself. it is practically not possible for long massages.
- We needed shorter key space for our long messages. But there is a problem, in order to guarantee information security, we needed to put our adversery under assumption of computationally bounded.
- Today crypto-systems that we use in practice can be broken easly if someone build a quantum computer with large number of qubits. So, We needed to avoid using the concept of short key. thus we needed to find some ways to produce more and more key as long as go i.e Alice can directly say into Bob's ear. Here the problem is Alice and Bob have exactly same key i.e the copy of Alice's Key send to Bob. An Easedroper can intercept the communication and try to listen it. It is the Symmetry Breaking Problem.
- Quantum Communication allows us to break the symmetry for this a no-cloning theorem exist which states that no qubits can be copied. Which provide security that easedroper can't copy the key and we can design some security protocols that allows Alice and Bob to produce key.
- Quantum Key Distribution(QKD) Protocol : it is secure agaist all power-full eavesdroper (arbitrarly large quantum computer)
- Quantum Cryptography started in 1970's when Stephen Wiesner had idea that quantum effects could be exploited in order to achieve cryptographic tasks.
- First QKD Protocol(BB84) Proposed by Bennett and Brassard in 1984.
- E91 Scheme which is based on the quantum entanglement by Arture Ekert. Thus the Quantum Entanglemet proved helpfull in order to understand QKD.

## 5. Conclusion
> Algebra, Number Theory, Lattice Theory, and Elliptice curves play a crusial role in the developement of cryptographic algorithms like Transposition cipher, Block Cipher, Shift Cipher, Affine Cipher, RSA etc.

> The Problem Sharing Key with Bob gives hacker advantage to intercept and decrypt the massage. But using QKD Protocols with the concepts of entanglement i.e E91 Protocol using it Alice can sent message as Bob at the same time reading it.