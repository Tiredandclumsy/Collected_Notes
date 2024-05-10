A cipher is a cryptographic algorithm that performs encryption/decryption. The study of ciphers is called [[Cryptology]]. 

The goal of a cipher is to ensure that only the intended recipient of the message can interpret it. Therefore, ciphers generally aim to achieve two key criteria:
- Unconditional security - a potential attacker cannot decrypt the enciphered message because they do not have the required information
- Computational security - the costs of breaking the cipher outweighs the usefulness of the [[Cryptology#Terminology|plaintext]]

# Types
## Substitution ciphers
A substitution cipher is any cipher that produced [[Cryptology#Terminology|ciphertext]] by replacing symbols in the plaintext. 
The simplest substitution cipher is the Caesar cipher, Generally, the alphabet of the message is sorted, and each $n$th alphabetical symbol in the plaintext is replaced by the $n+k$th symbol. [[modular numbers|modular arithmetic]] is used to 'wrap around' the alphabet, so that all values of $n+k$ are defined.
## Block ciphers
Block ciphers act on discrete blocks of plaintext. Each block cipher consists of an encryption and decryption algorithm, each taking a binary string of length $k$ called the key, and a block of length $n$. In the encryption algorithm this block is a binary section of plaintext, and ion the decryption it is a binary section of ciphertext. Each algorithm then outputs a binary string of length $n$. 
Given a certain key, the encryption and decryption algorithms must be inverse mappings of $\{0,1\}^n \to \{0,1\}^n$.

Block ciphers form the basis of most advanced cryptographic algorithms.
## Stream ciphers
Stream ciphers use a known algorithm generating pseudorandom bits from a given key to encrypt and decrypt messages. The plaintext in binary is compared with the pseudorandom bit string, and the corresponding bits of each are combined by an operator. This generates the ciphertext. The text is then deciphered by generating the same pseudorandom string, and reversing the operator to yield the plaintext. The bit operator used must therefore be reversible - XOR is most commonly used.

#cybersecurity 