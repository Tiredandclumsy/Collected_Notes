- [[#CIA Triad|CIA Triad]]
- [[#Cryptology|Cryptology]]
- [[#Ciphers|Ciphers]]
- [[#Keys|Keys]]
	- [[#Keys#Types|Types]]
		- [[#Types#Substitution ciphers|Substitution ciphers]]
		- [[#Types#Block ciphers|Block ciphers]]
		- [[#Types#Stream ciphers|Stream ciphers]]
- [[#Data Encryption Standard|Data Encryption Standard]]
- [[#Brute-force attacks|Brute-force attacks]]
	- [[#Brute-force attacks#Hash functions|Hash functions]]
		- [[#Hash functions#Message Authentication Codes|Message Authentication Codes]]
	- [[#Brute-force attacks#Digital Signatures|Digital Signatures]]
- [[#OSI Security Architecture|OSI Security Architecture]]
	- [[#OSI Security Architecture#Security attacks|Security attacks]]
	- [[#OSI Security Architecture#Security mechanisms|Security mechanisms]]
	- [[#OSI Security Architecture#Security services|Security services]]
		- [[#Security services#Authentication factors|Authentication factors]]
- [[#Threats|Threats]]
- [[#Attacks|Attacks]]
	- [[#Attacks#Man-in-the-middle attacks|Man-in-the-middle attacks]]
		- [[#Man-in-the-middle attacks#Eavesdropping|Eavesdropping]]
		- [[#Man-in-the-middle attacks#Replay attack|Replay attack]]
	- [[#Attacks#Impersonation attack|Impersonation attack]]
- [[#Networks and clients|Networks and clients]]
- [[#Network topology|Network topology]]
	- [[#Network topology#Circuit switching|Circuit switching]]
	- [[#Network topology#Packet switching|Packet switching]]
- [[#OSI Network Model|OSI Network Model]]
	- [[#OSI Network Model#Layer attacks|Layer attacks]]
- [[#Packets and frames|Packets and frames]]
- [[#Routers, bridges, hubs, and switches|Routers, bridges, hubs, and switches]]

# Basics of cybersecurity
Cybersecurity describes the practice of protecting computational systems, networks, and programs from malicious interference. It can be broken into information security, which protects data stored on computer systems, and network security, which protects networks and their services from unwanted interference while ensuring that they still perform their required functions.
## CIA Triad
The CIA triad defines three goals that a system should achieve:
- Confidentiality
	- Data confidentiality - Ensures that private or confidential information is not made available to unauthorised individuals
	- Privacy - Ensures individuals can control what information related to them is collected and stored by the system, as well as who has access to that information
- Integrity
	- Data integrity - Ensures information and programs are only altered by authorised individuals
	- System integrity - Ensures that a system performs its function unimpaired by unauthorised manipulation
- Availability
	- Availability - Ensures the system works promptly and service is not denied to authorised individuals
The triad can also be expanded with an additional two A terms:
- Authenticity
	- Ensures users can be identified and that input can be verified to originate from a trustworthy source
- Accountability
	- Ensures the actions of a person or account can be traced back to that person or account
## Cryptology
Cryptology is the study of encryption and decryption.
The study of encryption alone is known as Cryptography, and the study of decryption without knowledge of the encrypting details is called Cryptanalysis.
Cryptology has a set of key terminology:
- Plaintext: The original message to be encrypted
- Ciphertext: The coded message that must be decrypted to be read
- Enciphering or encryption: The process of converting plaintext into ciphertext
- Deciphering or decryption: The process of restoring plaintext from the ciphertext
- Cipher or Cryptographic system: A specific encryption/decryption algorithm pair
## Ciphers
A cipher is a cryptographic algorithm that performs encryption/decryption. The goal of a cipher is to ensure that only the intended recipient of the message can interpret it. Therefore, ciphers generally aim to achieve two key criteria:
- Unconditional security - a potential attacker cannot decrypt the enciphered message because they do not have the required information
- Computational security - the costs of breaking the cipher outweigh the usefulness of the plaintext
## Keys
Some ciphers require keys. These are secondary inputs to the cipher function that do not contain any information, instead they are used to further obfuscate the ciphertext. Keyed encryption algorithms attempt to give radically different outputs for identical messages and similar keys, or identical keys and similar messages. 
Some algorithms require two keys - one key is used to generate the ciphertext, and a different (ideally significantly different) key is used to recover the plaintext.
Ciphers that require only one key to encode and decode are called 'symmetric', and those requiring two keys are called 'asymmetric'.
### Types
#### Substitution ciphers
A substitution cipher is any cipher that produced ciphertext by replacing symbols in the plaintext. The simplest substitution cipher is the Caesar cipher. Generally, the alphabet of the message is sorted, and each $n$th alphabetical symbol in the plaintext is replaced by the $n+k$th symbol. Modular arithmetic is used to 'wrap around' the alphabet, so that all values of $n+k$ are defined.
#### Block ciphers
Block ciphers act on discrete blocks of plaintext. Each block cipher consists of an encryption and decryption algorithm, each taking a binary string of length $k$ called the key, and a block of length $n$. In the encryption algorithm this block is a binary section of plaintext, and ion the decryption it is a binary section of ciphertext. Each algorithm then outputs a binary string of length $n$. Given a certain key, the encryption and decryption algorithms must be inverse mappings of $\{0,1\}^n \to \{0,1\}^n$.
Block ciphers form the basis of most advanced cryptographic algorithms.
#### Stream ciphers
Stream ciphers use a known algorithm generating pseudorandom bits from a given key to encrypt and decrypt messages. The plaintext in binary is compared with the pseudorandom bit string, and the corresponding bits of each are combined by an operator. This generates the ciphertext. The text is then deciphered by generating the same pseudorandom string, and reversing the operator to yield the plaintext. The bit operator used must therefore be reversible - XOR is most commonly used.
## Data Encryption Standard
The Data Encryption Standard (DES) was issued by the National Bureau of Standards in 1977,  officially called the Federal Processing Standard 46. It sets out a cipher called the Data Encryption Algorithm, which encodes 64-bit blocks of plaintext with a 56-bit key into 64-bit blocks of ciphertext. It is a symmetric algorithm.
It was the most popular cipher until the introduction of the Advanced Encryption Standard (AES) in 2001.
## Brute-force attacks
A brute force attack describes any attempt to decrypt keyed ciphertext without exploiting any specific features of the cipher. This usually involves trying every possible key in the reverse function until intelligible plaintext is gained. On average, this requires attempting half the set of possible keys. 
### Hash functions
Hash functions are a type of cryptographic algorithm that take a variable length input and return a fixed length output that encodes the original input, usually with the goal of being computationally simple to calculate but practically impossible to reverse. Hash functions are not used to encode information directly, but instead can be used to verify that received data has not been tampered with or otherwise altered. A good hash function will output radically different strings for similar, but distinct, input strings.
Formally, hash functions aim to fulfil up to three criteria - for any hash function $H$:
- One way: it is difficult to find $m$ given $H(m)$
- Weak collision resistance: given $m$, it is difficult to find $m\prime \ne m$ such that $H(m) = H(m\prime)$
- Strong collision resistance: given $m_1,m_2$, $P(H(m_1) = H(m_2))$ is minimal
Hash collision (where two inputs generate the same hash) is impossible to avoid, as the range of the has function is by definition smaller than the domain due to the output's fixed size. The difference between weak and strong collision resistance can be illustrated in the birthday paradox - there is a much higher chance of any two people in a room having the same birthday than of two people both having a birthday on a given day.
#### Message Authentication Codes
Message Authentication Codes (MACs), use keyed hash functions to ensure message integrity. The hash function takes the message and a secret key, and produces a hash value (the MAC) associated with the message and key. Without the key of the function, any attacker can alter the message and run the hash function locally, appending the result. With the secret key, the attacker must have knowledge of the key to be able to generate the expected output.
### Digital Signatures
A digital signature is a piece of ciphertext generated from a data object that allows the recipient of the object to verify its integrity and origin. 
In practice, a user feeds the object to be sent into a digital signature generation algorithm, along with the user's private key. This creates a digital signature, which is sent along with the object. The recipient then uses the matching digital signature verification algorithm on the received signature, along with the first user's public key. This function returns whether the signature is valid, and if it is not then it is known that the object has been altered during communication.
## OSI Security Architecture
The Open Systems Interconnection (OSI) Security Architecture defines a systematic approach to providing security in a system. It is part of the larger OSI model, defined by the International Organisation for Standardisation (ISO). It defines categories for attacks, security defences, abstract layers on which attacks and defence strategies can act, and more. At the highest level, the OSI architecture is broken down into 3 categories: security attacks, security mechanisms, and security services.
### Security attacks
Security attacks are any attempts by people or entities to gain unauthorised access to a system. They are subdivided into 2 categories:
- Passive attacks
	Attacks in which a person or entity tries to access information about / stored within the system without authorisation
	Examples include eavesdropping and traffic analysis
- Active attacks
	Attacks in which a person or entity attempts to disrupt or alter the system. 
	Examples include masquerade, replay, message modification, and denial of service
### Security mechanisms
A security mechanism is any distinct process that attempts to prevent or identify security attacks. 
Examples include:
- Cryptographic algorithms
	Encipherment algorithms that encrypt data to be later decrypted
- Data integrity mechanisms
	Any mechanism that implements data integrity (a security service)
- Digital signature
	Data appended to, or a cryptographic transformation of, a message that allows the recipient to verify the source and integrity of the message
- Authentication exchange
	A mechanism implementing authentication via a specific exchange of information
- Traffic padding
	The insertion of arbitrary data into gaps in a data stream to frustrate attempts at analysis
- Routing control
	The ability to specify and alter the route of data through a network in the system, to allow rerouting in the case of compromised network sections
- Notarisation
	The use of a trusted third party to verify particular key properties of an information exchange, such as reliability and authority
- Access control mechanisms
	Any mechanism that enforce access rights to resources in the system, usually after a process of authentication
### Security services
A security service is any service available for maintaining the security and safety of a system.
These are subdivided into five categories:
- Authentication
	Providing the ability to identify entities interacting with the system
	Authentication exchange and notarisation achieve this
- Access control
	Preventing unauthorised access to the system or subsections of the system
	Routing control and access control mechanisms achieve this 
- Data confidentiality
	Protecting information in the system from being accessed by or disclosed to unauthorised parties
	Routing control, enciphering, and data padding achieve this
- Data integrity
	Ensuring data has not been altered by unauthorised parties
	Digital signatures and data integrity mechanisms achieve this
- Non-repudiation
	Provides a record of interactions with a system to prevent an individual from credibly denying undertaking a particular interaction
#### Authentication factors
In practice, authentication aims to pair a user with a unique 'digital identity' - a representation consisting of a set of attributes of a subject. The larger this set and more carefully selected the attributes, the more likely the digital identity is to be unique. This is not to be confused with identity proofing, which instead aims to establish the level of certitude that a user has, though identity proofing is usually achieved through authentication.
Authentication can be achieved by 3 factors, each of which defines a different kind of information a user can provide to prove their identity. 
1. Knowledge factor - something the user knows (e.g. password/PIN)
2. Possession factor - something the user has (e.g. key/OTP)
3. Inherence factor - something the user is (e.g. fingerprint/face ID)
Many systems defer use of factors to third parties, prompting the user to log into an external system that verifies their identity before redirecting back to the original page. This is called Federated Identity Management. 
## Threats
Threats in a system describe properties that allow attacks on the system to be successful. These threats can be information access threats, which allow attackers to access information that should be unavailable to them, of service threats, which allow attackers to disrupt the use of the system by legitimate users.
## Attacks
Attacks on computer systems come in various forms, but there are many common types that have been identified.
### Man-in-the-middle attacks
A man-in-the-middle (MITM) attack involves any attack where the attack positions themselves between two communicating parties, doing some combination of reading, relaying, and planting messages in the network connection.
#### Eavesdropping
A common MITM attack is active eavesdropping. An attacker poses as a communications channel, transparently relaying messages between two parties who believe they are communicating securely, allowing the attacker to read the contents of the messages.
#### Replay attack
A replay attack is a MITM attack where an attacker stores and later re-sends messages. For example, an attacker can obtain a secure key via eavesdropping, then later reuse this key to pose as another (possible higher certitude) user. This example is also an impersonation attack.
Replay attacks can be foiled by using sequence numbers and only accepting messages if their sequences are in order (not usually used due to relatively high overhead), using timestamps and only accepting messages received within a certain duration of their sending, or first sending out a dummy value and only accepting messages containing this value.
### Impersonation attack
An impersonation attack involves an attacker posing as another user of the system. This attack breaks authentication and non-repudiation.
# Basics of Network Security
A network is any system that permits single applications to run on a collection of separate hosts. The methods by which these hosts communicate is an obvious attack vector for jeopardising the network. 
## Networks and clients
Networks can be accessed by users via a terminal or a client. A terminal is a machine that does not do any local processing - it exists simply to interface with the network. A client instead performs local processing, communicating with the network and supplementing this communication with additional processes. 
A network is often abstracted by a client, such that the machinations of the machines in the network are unknown to the user.
## Network topology
Networks can be modelled as a graph, where individual hosts are nodes, and any two hosts that can communicate form an edge. It is not guaranteed that any message will be able to travel along a single edge from source to destination, and so some scheme of passing the message through the network must be devised.
### Circuit switching
The easiest scheme is network switching, where the entire message is routed through a particular path in the network, called a circuit. Once a circuit is found, it is retained for the entire communication session, and no other devices have access to the links in the circuit. It is commonly used for voice communication, such as telephone networks. Circuit switching offers reliable speeds, as the connections are only used fro that purpose, but does not scale for large numbers of messages in a network.
### Packet switching
Packet switching breaks the message into discrete packets, and sends each down a path to the destination. These paths can change if links in the network become unavailable. Packet switching scales well, as packets from multiple different messages can be sent down the same connections in succession.
Packet switching creates resource contention. Packets usually move in 'hops' through the network - upon arriving to a host, the host decides the next host the packet should be sent to, and so on. Therefore packets often must wait at a host for a connection to be available. 
## OSI Network Model
The Open Systems Interconnection (OSI) model is a standard created by the International Organisation for Standardisation (ISO) that described networked systems. It defines 7 layers, layer 1 being the lowest, of increasing levels of abstraction. Each layer has a dedicated unit of data, called a protocol data unit (PDU).
1. Physical layer - The lowest level, describes the transmission and reception of raw data over physical channels. PDU of bits or symbols. 
2. Data link layer - Describes the transmission of data frames between two nodes, including error correction. The data link layer controls the physical transmission and created frames and frame headers. Ethernet operates on this layer. PDU of frames.
3. Network layer - Describes the routing of data in a multi-node network, with operations such as addressing and traffic control. IP operates on this layer. PDU of packets
4. Transport layer - Ensures reliable relaying of data between hosts, including operations like acknowledgement and multiplexing. The transport layer also request the repeated transmisison of lost packets. TCP and UDP operate on this layer. PDU of segments or datagrams.
5. Session layer - Manages communication sessions, allowing the possibility of related back-and-forth transmission between two nodes. No PDU.
6. Presentation layer - Translates networked data into application-usable form, via decryption, decompression, and character encoding. No PDU.
7. Application layer - Governs high level protocols for resource sharing, remote access, and more. DNS and HTTPS operate on this layer. No PDU.
### Layer attacks
Attacks on networks target specific layers of the OSI:

| Layer           | Attack                                                                                                                                                                                                         |
| :-------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Application     | Repudiation, data corruption, file system bugs, file transfer exploits, protocol and version rollback attacks                                                                                                  |
| Presentation    | No common exploits                                                                                                                                                                                             |
| Session         | Remote Procedure call worms, port mapper exploits                                                                                                                                                              |
| Transport       | Routing protocol attacks, SYN flooding, sequence number prediction, session hijacking                                                                                                                          |
| Network         | IP smurfing, IP spoofing, wormhole / black hole / grey hole attack, byzantine errors, flooding, resource consumption, location disclosure, Sybil attacks, jellyfish attacks, fabrication, modification attacks |
| Data Link       | Traffic analysis, monitoring, MAC disruption, Wired Equivalent Privacy weakness, selfish-node exploits                                                                                                         |
| Physical        | Jamming, interception, eavesdropping                                                                                                                                                                           |
| **Multi-layer** | DoS/DDoS attacks, Impersonation, replay attacks, Man-in-the-Middle attacks                                                                                                                                     |
## Packets and frames
Frames are blocks of data created by network communication hardware, and contain the source and destination MAC address, as well as the data to be transferred.
Packets are blocks of data created by software, usually the Internet Protocol (IP). IP packets contain IP addresses and data.
In a network, a single packet travels from source to destination, but can be carrier by multiple frames depending on the number of routers it travels through.
The OSI makes a distinction between data links and physical links. Physical links are the connections between any two devices in a network, data links are the paths that frames take consisting of a chain of physical links, and a route is the path a packet takes consisting of multiple data links.
## Routers, bridges, hubs, and switches
Many devices exist to connect devices in a network, of varying complexities.
Routers use IP addresses to forward packets, and connect local networks to the internet.
Switches connect devices in local networks, routing frames to specific devices based on MAC addresses.
Hubs are simple devices that send incoming messages to all connected devices. They operate on the physical layer.
Bridges combine two otherwise separate networks into a single network by relaying frames. They operate in the data link layer.
## DNS
The Domain Name System allows a computer to locate a specific domain in the internet. It works by the computer querying a DNS server, which will return either the wanted domain, if in memory, or else return the IP of another server. Usually the query will rise up levels of breadth in a tree of connected servers until the server queried is a parent of the required server, at which point the query will pass down the tree to the wanted IP. An example of this is the following chain: ISP -> root server -> ..org server -> gnu.org, where the root server is the highest server in the tree.
Historically, DNS was a cleartext (un-encrypted) system using TCP/UDP on port 53 of a device, which was vulnerable to monitoring, redirection, and blocking. 