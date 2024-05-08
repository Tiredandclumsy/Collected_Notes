Hash functions are a type of [[cipher|cryptographic algorithm]] that take a variable length input and return a fixed length output that encodes the original input.
Hash functions are not used to encode information directly, but instead can be used to verify that received data has not been tampered with or otherwise altered.
A good hash function will output radically different strings for similar, but distinct, input strings.

# Message Authentication Codes
Message Authentication Codes (MACs), use keyed hash functions to ensure message integrity. 
The hash function takes the message and a secret key, and produces a hash value (the MAC) associated with the message and key.
Without the key of the function, any attacker can alter the message and run the hash function locally, appending the result. With the secret key, the attacker must have knowledge of the key to be able to generate the expected output.

#cybersecurity