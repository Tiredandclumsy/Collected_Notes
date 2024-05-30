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
	- [[#Attacks#Denial-of-Service attack|Denial-of-Service attack]]
	- [[#Attacks#Protocol attacks|Protocol attacks]]
- [[#Networks and clients|Networks and clients]]
- [[#Network topology|Network topology]]
	- [[#Network topology#Circuit switching|Circuit switching]]
	- [[#Network topology#Packet switching|Packet switching]]
- [[#OSI Network Model|OSI Network Model]]
	- [[#OSI Network Model#Layer attacks|Layer attacks]]
- [[#Packets and frames|Packets and frames]]
- [[#Routers, bridges, hubs, and switches|Routers, bridges, hubs, and switches]]
- [[#IP and MAC addresses|IP and MAC addresses]]
	- [[#IP and MAC addresses#IP Spoofing|IP Spoofing]]
	- [[#IP and MAC addresses#IPsec|IPsec]]
		- [[#IPsec#Sub-protocols|Sub-protocols]]
		- [[#IPsec#IPsec control modes|IPsec control modes]]
		- [[#IPsec#Security Associations|Security Associations]]
- [[#VPNs|VPNs]]
	- [[#VPNs#L2TP|L2TP]]
- [[#SSL|SSL]]
- [[#TLS|TLS]]
- [[#HTTP|HTTP]]
	- [[#HTTP#HTTPS|HTTPS]]
	- [[#HTTP#Application layer attacks|Application layer attacks]]
- [[#TCP|TCP]]
	- [[#TCP#TCP attacks|TCP attacks]]
		- [[#TCP attacks#SYN flooding|SYN flooding]]
- [[#DNS|DNS]]
	- [[#DNS#DNS attacks|DNS attacks]]
	- [[#DNS#Encrypted DNS|Encrypted DNS]]
- [[#Smurf attack|Smurf attack]]
- [[#Jamming|Jamming]]
- [[#SQL injection|SQL injection]]
- [[#Cross-site scripting|Cross-site scripting]]
- [[#Firewalls|Firewalls]]
	- [[#Firewalls#Policy control|Policy control]]
	- [[#Firewalls#Types of firewall|Types of firewall]]
		- [[#Types of firewall#Packet filtering|Packet filtering]]
		- [[#Types of firewall#Application level|Application level]]
		- [[#Types of firewall#Stateful inspection|Stateful inspection]]
		- [[#Types of firewall#Circuit level gateways|Circuit level gateways]]
		- [[#Types of firewall#Personal firewall|Personal firewall]]
- [[#Intrusion Detection Systems|Intrusion Detection Systems]]
	- [[#Intrusion Detection Systems#Types of IDS|Types of IDS]]
	- [[#Intrusion Detection Systems#IDS responses|IDS responses]]
	- [[#Intrusion Detection Systems#False results|False results]]
- [[#Intrusion Prevention Systems|Intrusion Prevention Systems]]
- [[#Memory corruption bugs|Memory corruption bugs]]
- [[#Pointers|Pointers]]
- [[#Memory safety|Memory safety]]
- [[#Safety in C|Safety in C]]
- [[#Buffer overflow|Buffer overflow]]
- [[#Format string errors|Format string errors]]
	- [[#Format string errors#%n|%n]]
- [[#Privilege levels|Privilege levels]]
	- [[#Privilege levels#Processor|Processor]]
	- [[#Privilege levels#Memory|Memory]]
	- [[#Privilege levels#Changing levels|Changing levels]]
		- [[#Changing levels#Events|Events]]
- [[#Abstraction|Abstraction]]
	- [[#Abstraction#Processes and Threads|Processes and Threads]]
- [[#Memory layout|Memory layout]]
- [[#Virtual memory|Virtual memory]]
	- [[#Virtual memory#MMU|MMU]]
	- [[#Virtual memory#Page faults|Page faults]]
		- [[#Page faults#Replacement policies|Replacement policies]]
- [[#History of operating systems|History of operating systems]]
	- [[#History of operating systems#Phase 0 - No OSes (1940-1955)|Phase 0 - No OSes (1940-1955)]]
	- [[#History of operating systems#Phase 1: Batch monitors (1950-1970)|Phase 1: Batch monitors (1950-1970)]]
	- [[#History of operating systems#Phase 2: Multiple users (1970-1980)|Phase 2: Multiple users (1970-1980)]]
		- [[#Phase 2: Multiple users (1970-1980)#UNIX|UNIX]]
- [[#Phase 3: Cheaper hardware (1980-1990)|Phase 3: Cheaper hardware (1980-1990)]]
- [[#Phase 4: Networked systems (1990-)|Phase 4: Networked systems (1990-)]]
- [[#Phase 5: Something new (????-????)|Phase 5: Something new (????-????)]]
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
### Denial-of-Service attack
A Denial-of0Service (DoS) attack is when an attacker attempts to make a resource unavailable to its users. The most common form is a Distributed Denial-of-service (DDoS) attack, where multiple (usually compromised) machines are used to flood a network.
### Protocol attacks
A protocol attack is any cyberattack that exploits a feature of a particular internet protocol. 
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
## IP and MAC addresses
Internet Protocol (IP) addresses are either 32-bit (IPv4) or 128-bit (IPv6) numerical labels used to route packets through the internet, in the network layer. Medium Access Control (MAC) addresses are 48-bit addresses that allow routing of datagrams to end devices in the data-link layer. 
The Address Resolution Protocol (ARP) handles the switch between IP and MAC addresses, with routers having ARP tables that match IPs to MAC addresses. These tables are populated by sending requests containing an IP to be added to the table, and the IP of the device storing the table. These propagate through the network, and the device with he requested IP then sends its MAC address to the second IP in the request.
ARP tables are relatively easy to spoof, as they are updated frequently, so a malicious actor can fulfil ARP requests to redirect network traffic. Static ARP addresses (that aren't forgotten) help frustrate this, and there are software packages that help detect ARP spoofing, but it cannot be prevented. 
### IP Spoofing
IP spoofing refers to the creation of IP packets with false source IP addresses in order to impersonate another system.
IP spoofing can be used to bypass filtering systems such as firewalls, or perform DoS attacks by requesting a large quantity of data while appearing as the victim system.
### IPsec
IPsec (Internet Protocol security) is a  standard first defined by the Internet Engineering Taskforce (IETF) in 1995, which was revised in 1998 and 2005.
IPsec begins with an initialisation phase. This requires both devices to verify the other with a public key, then establishes and further verifies with a shared private key. The phase also includes negotiating security services and mechanisms. The phase is protected in integrity and authenticity, and is governed by the Internet Key Exchange (IKE) module, running on the application layer.
The standard also includes a data protection phase. This phase uses  symmetric encryption to create a protected tunnel that secures packet flow, ensuring confidentiality, integrity, and authentication. It's implemented by either the Authentication Header (AH) or Encapsulating Security Payload (ESP) sub-protocols. 
#### Sub-protocols
There are two sub-protocols of note in IPsec:
AH (protocol 51) ensures integrity and authentication of origin, and optionally ensures replay detection. It protects the packet content and a section of the header.
ESP optionally ensures data confidentiality; and integrity, authentication of origin, and replay detection. It only protects the packet content.
The key exchange protocol (IKE) permits multiple different methods of key exchange depending on the section of IPsec being performed:

| Key exchange method                                                                                          | IPsec stage                                                   |
| :----------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------ |
| 3DES-CBC (encryption)<br>HMAC-SHA1  (PRF)<br>HMAC-SHA1-96 (integrity check)<br>1024-bit MODP (DH Group)      | 3DES-CBC (encryption)<br>HMAC-SHA1-96 (integrity)<br>ESP      |
| AES-128-CBC (encryption)<br>AES-XCBC-PRF-128 (PRF)<br>AES-XCBC-MAC96 (integrity)<br>2048-bit MODP (DH Group) | AES-128-CBC (encryption)<br>AES-XCBC-MAC96 (integrity)<br>ESP |
Where PRF denotes a pseudo-random function, and MODP denotes a modular exponential function.
#### IPsec control modes
IPsec permits two modes of data transfer.
Transport mode simply wraps the data in a packet and sends it. This protects the packet contents and IPsec defined sections of the header, but leaves the rest of the header unencrypted.
Tunnel mode takes the transport mode packet and wraps it in another IPsec packet, protecting the entire original packet, leaving only a section of a new IP header unencrypted. This wrapping is usually done by another device, in the context of a VPN.
#### Security Associations
Security Associations (SAs) are contracts formed between to devices to specify the parameters of a secure connection. They contain a list of a security protocol (AH or ESP), the status of the optional services for each, encryption algorithms, encryption keys, an initialisation vector, a hash function, an IPsec control mode, and a lifetime for the SA. These parameters are usually combined into three values - one called the Security Parameters Index (SPI), one for the address of the IPsec equipment, and one to define the security protocol (AH or ESP). 
## VPNs
A Virtual Private Network uses an IP tunnel to exchange data between parties. This is useful for facilitating communication between parties where security is required, such as within a distributed company, between a company and its partners, etc. They can be used to interconnect LANs via IPsec, or permit remote access into a LAN from a nomad machine using either IPsec or TLS.
The VPN is created by forming a tunnel - the packets are created as though in a local network, then wrapped in intern-ready IP packets before being sent. They are then unwrapped at the receiving end, allowing local network-like communication over public internet. IPsec and TLS are used to ensure the CIA triad. 
VPN protocols contain an initialisation phase of authentication, key exchange, and security negotiation, and a data protection phase where negotiated security services are activated.
VPN gateways (devoices that wrap packets) authenticate each other via public and private key exchange. Users authenticate with gateways via passwords.
# Clientless/client-based
A clientless VPN involves the nomad connecting to the gateway directly via an HTML/TLS connection in a browser. This setup is easier to manage and has lower cost, as well as the fact that it does not require the nomad to install a client. However it has restricted access to services, as all communication must be done through the browser.
A client-based VPN runs on a client program on the nomad's device, which forms an IP/TLS connection to the gateway. This allows access as thought the nomad was part of the local network, but requires installation of an IPsec and/or VPN client on the nomad device depending on use case.
IPsec is a common solution for VPNs and is heavily optimised for VPN formation, but is heavy to manage due to IKE processes. TLS on the other hand is the most common solution for clientless VPNs, and is lighter on processing, bur limits the use of certain applications.
### L2TP
The Layer Two Tunnelling Protocol, first established in 1999, is the standard for forming tunnels in VPNs, specifically VPNs between private networks and nomads. It requires an L2TP client running on the nomad, and a L2TP Network Server (LNS) running within the local network's IPsec gateway.
L2TP first establishes an IPsec session to protect packets, then authenticates the nomad's device. Then, an L2TP tunnel is established, in which the nomad is given a private address and the user is authenticated.
Microsoft has its own proprietary standard that supports encryption - the Point to Point Tunnelling Protocol (PPTP).
## SSL
The Secure Sockets Layer is the first web encryption standard, released by Netscape in 1995. It encrypts between the application and transport layers, and was the first encryption used by HTTP to form HTTPS. It has now been almost entirely replaced by TLS. The last SSL standard was version 3.0, released in 1996. SSL was officially deprecated in 2015 by the Internet Engineering Taskforce (IETF).
## TLS
TLS, or Transport Layer Security, is the current standard for network encryption. 
TLS requires an initialisation phase to form a connection before communication can take place. The server authenticates the client with its public key certificate, after which security mechanisms and services are negotiated. A secret 'master' key is established, and then communication proper can begin. This phase fulfils integrity and authenticity, and is governed by the TLS Handshake Protocol. Other functions of the handshake include agreeing on the TLS version, replay detection, and detection of message integrity issues. 
In TLS 1.0-1.2, a data protection phase also occurred, governed by the TLS Record Protocol. This stage breaks the data into fragments, compresses them, encrypts them, and appends a Message Authentication Code to each. This phase used symmetric encryption as protection, and ensured confidentiality, integrity, and authentication.
Other parts of the TLS protocol include the TLS Change Cipher Spec Protocol, TLS Alert Protocol, and TLS Application Data Protocol.
Standards that use SSL or TLS are renamed with an additional 'S' - HTTPS, FTPS, etc. 
The entire TLS exchange is as follows (where -> means client to server, and <- is server to client):
1. Handshake: ClientHello ->
2. <- Handshake: ServerHello
3. <- Handshake: Certificate
4. <- Handshake: ServerHelloDone
5. Handshake: ChangeCipherSpec ->
6. Handshake: ClientFinished ->
7. <- Handshake: ChangeCipherSpec
8. <- Handshake: ServerFinished
9. <- application data transfer ->
10. Alert: CloseNotify ->
TLS uses the following possible protocols:

| Key exchange | Encryption algorithm | Hash function |
| :----------- | :------------------- | :------------ |
| RSA          | RC4_128              | MD5           |
| DH_DSS       | 3DES_EDE             | SHA-1         |
| DH_RSA       | AES_128_CBC          | SHA-256       |
| DHE_DSS      | AES_256_CBC          |               |
| DHE_RSA      |                      |               |
| DH_anon      |                      |               |
## HTTP
The Hypertext Transfer Protocol (HTTP) is an asymmetric request-response protocol defining client-server transfer of data. It is a pull protocol, meaning the client sends a request message, prompting data to be sent back by the server. This is in contrast to a push protocol, where the server sends the data without a request.
It exists on the application layer, utilising TLS in the transport layer to encrypt its communications (forming HTTPS) and IP on the network layer to locate servers and clients.
HTTP session hijacking involves an attacker injecting a malicious script into a server, which then sends the script to a user as the result of an HTTP request. The script is then executed on the user's system. 
HTTP session side jacking involves an attacker sniffing the contents of HTTP packets to gain data such as authentication cookies, which can then be used to gain access to the server. This is only possible if a portion of the session is unencrypted, and if the attacker ahs access to the user's wiki network, and so typically occurs on unsecured WIFI hotspots.
### HTTPS
HTTPS encrypts HTTP packets using TLS. It encrypts most data in the packet, but leaves the remote address and request URL header.
### Application layer attacks
Attacks exploiting HTTP involve sending large volumes of HTTP requests that exhaust a target server's ability to respond. This is a particular application level DDoS attack known as a 'level 7 attack'. Malicious HTTP requests are often hard to filter, and so this attack is difficult to counter.
## TCP
Transmission Control Protocol (TCP) is a standard that facilitates reliable, ordered, and error-checked delivery of packets. It operates on the transport layer.
TCP requires a connection to be set up between the two communicating devices. This involves 3 messages utilising 3 values - SYN and ACK flags (1 bit), and seq and ack values (32 bits). First, the client sends a message with high SYN and some client value of seq. Then the server responds with SYN and ACK high, ack set to the received seq value plus 1, and seq set to some new sever value. Then the client responds finally with ACK high, seq set to the received ack value, and ack set to the received seq value plus 1.
### TCP attacks
The handshake involving large entropy of seq and ack values makes TCP sessions very hard to attack once established. However, if the attacker is on the same network as the client, they can sniff the TCP packets and complete the handshake from their machine, forming the communication channel posing as the client's machine, while locking the client out of the handshake. This is called TCP session hijacking. To hijack the session, IP spoofing must be used, since the server checks that all messages in the handshake are from the same IP.
#### SYN flooding
An attacker can perform a DoS attack on a server by sending multiple SYN requests to a server. The server responds to these with SYN-ACK messages, and stores the required values in memory to verify the response of each. This use of memory leads to the server being overwhelmed, and rejecting any other SYN requests. If the attacker never sends any ACK responses to form a connection then the server remains unavailable. usually attackers use multiple spoofed IP addresses to obfuscate their identity and make blocking IPs more difficult.
SYN flooding can be tackled in multiple ways. Ingress filtering describes blocking incoming packets at edge devices (routers, firewalls, etc) based on the contents of their headers, usually the origin IP. Unicast Reverse Path (uRPF) checks allow edge devices to reference IPs on a table and ensure that packets came from the expected 'ingress interface', meaning the traffic was previously routed through the expected section of the network. This becomes more difficult when multiple paths are possible, or when the best route from node A to B is different from the best route from B to A (asymmetric routing). Finally, a SYN cookie system for TCP can be used, that encodes the server seq value with some function of the server and connection's traits, and the ack response can be referenced against this value without having to store it, with the seq value discarded. This allows any number of SYN-ACK messages to be pending at once.
## DNS
The Domain Name System allows a computer to locate a specific domain in the internet. It works by the computer querying a DNS server, which will return either the wanted domain, if in memory, or else return the IP of another server. Usually the query will rise up levels of breadth in a tree of connected servers until the server queried is a parent of the required server, at which point the query will pass down the tree to the wanted IP. An example of this is the following chain: ISP -> root server -> .org server -> gnu.org, where the root server is the highest server in the tree.
Historically, DNS was a cleartext (un-encrypted) system using TCP/UDP on port 53 of a device, which was vulnerable to monitoring, redirection, and blocking. 
### DNS attacks
DNS is therefore a vulnerable target for eavesdropping, especially as the entire request information is available at all levels of resolution. Posing as a DNS server and maliciously resolving requests is called DNS hijacking. 
DNS also uses caches, where commonly requested domains are stored in root servers to speed up resolution. This means malicious actors can pose as a DNS server and fulfil a root's request, where the malicious request is then cached and passed to all users of the root server without further intervention of the attacker. This attack is called DNS cache poisoning. 
DNS amplification attacks are DDoS attacks that make repeated DNS requests with a spoofed IP, meaning DNS resolvers send the resulting addresses to a target machine, overwhelming it.
### Encrypted DNS
The first encrypted system for DNS was DNS over TLS (DoT), released in 2016. It uses the Transport Layer Security protocol to wrap DNS packets, and sends them on port 853. This system established a secure channel between the client and any used resolver servers, preventing plaintext eavesdropping. 
DNS over HTTPS (DoH) was introduced in 2018 as an alternative to DoT. It uses HTTPS to encode the DNS packets, sending them on port 443 like all HTTPS requests. HTTPS utilised TLS in its encryption.
## Smurf attack
A smurf attack is a specific DDoS attack in which multiple Internet Control Message protocol (ICMP) packets are sent to a computer network, with each packet listing the same victim IP address as its origin. The ICMP dictates that packets should be acknowledged with a return packet by default, and so the network responds by sending a large number of packets to the victim's IP, flooding it with traffic. 
## Jamming
Jamming involves positioning a transmitter to add interference to a communication channel, usually by broadcasting noise on specific wireless frequency bands. This increases error rate of transmission to prevent useful communication between devices. It operates on the physical layer. 
# Basics of internet security
Internet security, also called web security, is the study of systems to keep users and devices safe from cyberattacks when connected to the internet. Threats that internet security can help protect against include phishing, SQL injection, cross-site scripting, and more.
## SQL injection
SQL injection involves using a client-side interface with a server to 'inject' and run malicious SQL queries, causing the server to respond with unintended data.
## Cross-site scripting
Cross-site scripting (XSS) involves an attacker loading malicious code onto a website, which is downloaded and executed on a victim's machine when the website is loaded. Most simply, it involves appending the URL of the malicious code as message entry to the end of the original website URL.
## Firewalls
Firewalls are systems that filter traffic entering a pre-defined internal network. They usually run on dedicated devices to maximise performance and minimise possible security breaches. Firewalls either permit all traffic that is not explicitly forbidden (default permit), or vice verse (default deny). 
Firewalls provide a single focal point for network monitoring and access control, and layers of firewalls can isolate discovered threats to subsections of the network. However, they cannot protect against attacks that have already passed through them, new threats that are not yet blocked, attacks that do not enter the network through the internet or enter through a trusted source, and they cannot provide protection against legitimate malicious users.
Firewalls can be stacked, creating multiple levels of access control. This can be used to provide protected internal networks for more secure data or higher profile users. 
Firewalls can also keep logs of traffic for later inspection.
### Policy control
Firewalls can enforce control in three ways:
- Service control - determining which internet services can be accessed
- Direction control - determining which direction internet services are permitted to act in
- User control - determining who can access which internet services (usually via IP)
### Types of firewall
There are different types of firewall based on OSI level, state memory, and specific function.
#### Packet filtering
Packet filtering is the simplest kind of firewall, and is often very effective. It works on the network layer, blocking based on IP address and transport protocol (e.g. blocking insecure HTTP packets). They are stateless, and usually have fast processing speeds. However, they lack upper-layer functionality such as blocking specific application functions, and don't support advanced user authentication schemes.
#### Application level
Also called an application proxy, and application level firewall relays and filters application information to users. They can offer advanced authentication schemes giving a high level of security, and their abstraction makes them easy to understand, but they suffer additional processing overhead and can affect network performance.
#### Stateful inspection
Stateful inspection firewalls maintain state information from one packet to the next in the scrutinised data stream. This allows the foiling of attacks that are split into multiple packets in an attempt to exploit the fact that TCP packets arrive in any order. A stateful inspection firewall can record and reconstruct the message from multiple out-of-order packets to identify and prevent the attack.
#### Circuit level gateways
A circuit-level gateway, or circuit-level proxy, prevents end-to-end TCP connections from forming, and instead forms TCP connections between it and both communicating parties, permitting additional regulation of permitted connections. Circuit-0level gateways can be standalone, or act as a service provided by an application level firewall. 
#### Personal firewall
A firewall-like program can be run on a single device, which blocks certain incoming traffic packets based on predefined rules. These programs are personal firewalls, and can make up for shortfalls in network firewalls.
## Intrusion Detection Systems
Intrusion Detection Systems (IDSs) monitor activity on a network to identify suspicious or malicious events. They can also assess the integrity of systems and files, notice violation of user policy, analyse user activity for suspicious behaviour, and correct system configuration vulnerabilities, amongst other functionality. 
IDSs should be able to react in a timely fashion to attacks, identify the precursors to more serious threats, discover the perpetrator of attacks, reveal attack patterns, and produce convincing evidence to motivate further action.
### Types of IDS
IDS that have a predefined pattern of malicious activity to flag are 'signature based' while those that build a model of malicious behaviour are 'heuristic'.
A network-based IDs is deployed on a dedicated machine and monitors the entire network, but a host-based IDS runs as a process on a host machine and acts on traffic into and on that machine.
IDSs can also act top report any behaviour that is seen as malicious (and default to not reporting), which leads to a Misuse Detection System, or report any behaviour outside of what is deemed normal (defaulting to reporting), leading to an Anomaly Detection System. Current IDS design trends are shifting towards a hybrid of these approaches.
### IDS responses
When an IDS flags malicious behaviour, it had a set process to respond. The responses tend to fall under three categories:
- Collect data / monitor threat
- Protect network and reduce exposure
- Alert a human user
### False results
IDSs can make two types of false error - a type I error (false positive) or a type II error (false negative). Type I errors erode trust in the IDS, but type II errors lead to undetected attacks.
The detection rate of an IDS is defined as the proportion of attacks that were detected: $\text{DR} = \cfrac {\text{TP}}{\text{TP}+\text{FN}}$, and the precision is the proportion of detections that found attacks: $\text{Precision} = \cfrac {\text{TP}}{\text{TP}+\text{FP}}$. An IDS should seek to minimise these values.
## Intrusion Prevention Systems
Intrusion Prevention Systems (IPSs) are a combination of a firewall and IDS. They offer the ability of the two systems to work together, with the IDS relaying information to firewalls to contain attacks and prevent future attacks with similar patterns.
# Basics of Software Security
Software security involves ensuring that programs do not violate the security principles of the data they interact with.
## Memory corruption bugs
In memory unsafe languages, code can be written that allows the modification of memory beyond intended specifications. Any bug in software that permits this modification is said to have a memory bug. Memory corruption bugs can lead to arbitrary read and write, as well has control flow hijack and corruption.
## Pointers
Pointers in C, as well as pointer abstractions like objects in Kava, are prone to cause memory bugs. In general, once the user has managed to get a pointer indexing a memory location that the pointer is not designed to, a memory bug has occurred.
## Memory safety
Memory safety must hold in two regards:
- Spatial safety - pointers must not access locations outside the bounds of allocated objects. Violation of spatial safety includes attacks like stack smashing. 
- Temporal safety - pointers must not be used to reference objects that have previously been deallocated. Violation of temporal safety includes attacks like heap overflow.
## Safety in C
Indexing an array with a negative value in C gets a warning, but is permitted by the C standard and so compiles and runs, causing a spatial error.
Additionally, functions such as `gets()` and `strcpy()` can lead to buffer vulnerabilities, and so throw warnings when compiled. `gets()` copies input from the user into memory, and `strcpy()` copies an input string into a specific array. Safer versions of these functions, `fgets()` and `strncpy()` respectively, are now implemented in most C compilers.
## Buffer overflow
Buffer overflow is an old, but still very common, cause of vulnerabilities, where more data is placed input into a system than anticipated, leading to memory overwriting. 
Many locations in memory are predictable, and so it is relatively easy given a buffer exploit to write executable code to the stack, for example. 
Modern CPUs have privilege levels that prevent programs from writing to sections of memory they should not have access to. However this can be circumvented with libc or ROP. To help with these exploits there are a few measures - stack canaries are values placed before the return address that are investigated to ensure they have not changed due to buffer overflow, and shadow stacks are copies of the main stack with return addresses that can be cross-referenced to ensure consistency.
## Format string errors
Format strings consist of normal characters and conversion specifiers. When passed to a formatted output function such as `printf()` the conversion specifiers change based on a set of instructions and the other inputs to the function, creating a string of normal characters. Conversion characters begin with a `%` sign, and are mapped to inputs left-to-right. If there are not enough arguments for all specifiers the results are undefined, and if there are too many the additional inputs are rejected.
Functions `sprintf()` and `vsprintf()` assume an arbitrarily large number of conversion specifiers, each accepting arbitrarily large input, and so it is often impossible to assure that the output string will fit within any allocated memory space.
### %n
The `%n` specifier is an outlier, in that it does not alter the output string, but instead writes to memory. Its corresponding additional input is a numerical pointer, and the `%n` specifier causes the number of previously printed characters to be stored in this memory location. This memory writing, along with careful input selection, can permit arbitrary addresses after the stack pointer to be written to. If these addresses are variables then data corruption can occur, and if they are return addresses then data flow corruption and arbitrary code execution can occur.
# Operating Systems
Operating Systems (OSes) are packages of software that manage computer hardware resources. In general, they are programs that implement multiplexing and abstraction of hardware - multiplexing allows multiple users to make use of the same set of hardware resources, and abstractions simplify interaction with hardware resources by defining rules under which the hardware can be interacted with.
## Privilege levels
### Processor
Operating Systems also exist as a boundary that protects hardware and low-level software interfaces from misuse by programs and applications. This is done through privilege levels -  modern processors have at least 2 levels: a user space where regular programs run, and a kernel mode that runs the operating system and allows it to implement memory protections. Processor modes dictate which instructions can execute, how addresses are translated from virtual memory, and what memory addresses are permitted to be accessed.
x86 specifies 4 modes. Ring 0 is the most privileged and runs the kernel, rings 1 and 2 are rarely used and exist to run third party drivers or virtual monitors, and ring 3 handles all other processes. 
MIPS (Microprocessor without Interlocked Pipelined Stages) defines a standard two-mode processor - user mode can access CPU registers and a uniform virtual memory space, whereas kernel mode can access memory mapping hardware and spatial registers.
### Memory
Memory also has a concept of privilege levels. Each segment of memory is given a level 1 to 3, which is stored in the processor's CPL (Current Privilege Level register) when an instruction is read from that segment. The instruction is then executed if the CPL is is less than or equal to the current IOPL, which is a flag set by programs running on ring 0.
### Changing levels
The changing of privilege levels is tackled in different ways by different processors and systems:
The Sleeping Beauty approach exists in the lowest privilege mode until some event occurs that 'wakes' the kernel and raises the privilege. These events include system calls, traps or interrupts. 
The Alarm Clock approach sets a timer when the system drops from kernel mode, and raises an interrupt once a certain amount of time has passed, where the system returns to kernel mode and deals with any required tasks.
#### Events
A system call is a method of permitting interaction between programs and the operating system. The functionality of the OS is abstracted into an API that programs use when making a system call.
A trap is triggered by an exception or error in a process, usually on conditions such as dividing by zero, hitting a breakpoint, or accessing an invalid memory location. Once th cause of the exception has been handled, the processor returns to its previous privilege level.
An interrupt is a signal from hardware or software that demands OS attention. It differs from a trap in that it can be asynchronous, and it not handled as part of the program that caused it. Since they can be caused by hardware, they may not have any effect on the currently running process.
## Abstraction
Abstraction, in terms of operating systems, refers to the simplification of hardware interaction by an interface separating policy (what is accomplished by the interface) from mechanism (how the interface works). This hides undesirable properties, adds new capabilities, and organises information.
For example, threads are an OS abstraction of the CPU, address space is an OS abstraction of physical memory, and files are an OS abstraction of the disk. Files specifically help hid the undesirable properties of fragmentation and storage failure, add organise via directories, and add additional features of ownership, RWX permission, filetype, access time logs, and more.
### Processes and Threads
Threads and processes both abstract functions of the CPU, but are not the same. Threads describe discrete sections of the CPU used to run tasks, and processes describe collections of tasks that achieve the same goal. Processes consist of CPU resources as well as relevant files and memory locations. A process therefore contains threads, and threads belong to a process. A process is said to be running if at least one of its threads are running.
An example of a process is a browser - it has multiple threads for processing interface events, drawing to the screen, loading web page information, etc; memory locations for the executable code, shared libraries such as TLS/SSL used to process internet data, dynamically allocated memory for variables, etc; and files on disk open including fonts and config files.
## Memory layout
A C program has an allocated amount of memory defined by a low address and a high address. From the low address up, there are the following blocks:
- Text - stores the code of the program
- Initialised data - contains global variables, static variables, and values of constants
- Uninitialised data - contains any variables not initialised, as this section is initialised to all 0s by the kernel before execution
- Heap - location of dynamic memory allocation, managed by `malloc()`, `realloc()`, and `free()`. Generally grows into larger memory values - 'grows up'.
- Stack - the stack is a dynamic LIFO structure that stores return values and automatic variables. Its current size is defined by a stack pointer, and in x86 it grows towards lower memory values - 'grows down'. 
When heap and stack pointers meet, the memory of the program is used up. If multiple programs are owned by the same process, then each get their own stack, but heap memory is shared. 
## Virtual memory
Physical memory is finite, and shared between all processes. Some system must be put in place to avoid processes writing to other processes' memory, and this system is the OS. The OS allocates each process a section of virtual memory (in MIPS virtual memory is allocated in 32-bit blocks) which holds data, code, and stacks for the process. No two sections of virtual memory overlap.
### MMU
The MMU is a hardware module that translates virtual memory addresses (generates by processes) into physical memory addresses  (given to the RAM). It is only configurable by the kernel. 
Early attempts at this mapping defined a base and bound - a start location and a size of the block. This allowed different sizes of memory space, easy conversion to physical addresses, and simple insurance of isolation. However, it wasted any space within the block that was not used (like space between stack and heap), did not support RWX privilege, and only allowed memory sharing between two processes via overlap. 
Another option is segmentation. This defines a base, bound, and RWX permission set for a program's code, static data, heap, and stack. This allows any number of programs to share physical memory, while preventing overwriting, and wastes less memory than base and bound. However, if the actual memory needed is small then more memory can be used storing the mapping than is actually needed. 
Modern systems use a scheme known as pages. Memory is split into blocks, called pages, and each is addressed with a number and an offset determining the location within the page. Pages are small enough to not waste space and to be practical to quantise all memory on the device. However, their size comes with the drawback of their numbers - small pages mean lots of pages to keep track of, and bookkeeping therefore becomes more complex.
Pages can be swapped from RAM to disk, and moved back when needed, creating a virtual memory that is much larger than the physical memory available. 
### Page faults
When the MMU attempts to access a page that is on disk and not memory, it raises an exception called a page fault. The kernel then swaps the requested page from disk into memory, evicting another page if necessary, before deferring back to the MMU so it can attempt to access the page again. Interacting with disk is slow - around 1000 times slower than RAM, and so page faults occurring every $n$ accesses results in a system $1000^{\frac 1 n}$ times slower than it could be. Thus page faults must be minimised. This is done by making the replacement policy (deciding which pages to evict to make way for a new one) as optimal as possible.
#### Replacement policies
First In First Out (FIFO) evicts the page that has been in memory the longest. 
Least Recently Used (LRU) evicts the page that has not been referenced for the longest.
MIN is the ideal scheme, which evicts the page that will not be needed for the longest. However it cannot be completely implemented in practice. 
A Second Chance policy, also known as a clock policy is a practical middle-ground, where a used bit is added to the page table for each page. It is set to 1 by the MMU when the page is first put up for evicting, and set to 0 by the kernel when the page is accessed. If a page with a used bit of 1 is inspected for eviction again, it is evicted.
## History of operating systems
### Phase 0 - No OSes (1940-1955)
At this stage, computers are experimental and exotic machines. They are programmed in machine code with plugboards and/or punch cards, and are intended for large or repetitive calculations. People begin developing libraries of code to share for common tasks.
### Phase 1: Batch monitors (1950-1970)
Computers are first given terminals, and basic OSes. These are batch monitors, that load a task that a user has specified, run it, and then load the next task. If a program fails it is saved to memory, but computers begin to gain the ability to move on from failed programs and load the next task. Batch monitors allow efficient use of hardware.
As this phase develops, it becomes apparent that serial task management is not sufficient. Short jobs are continually stuck behind long ones, and there is no memory protection between jobs. Hardware is therefore developed that permits memory protection (separation of code and data), multiple users on one system, and scheduling. OS design forms as an area of research. OS/360 is released in 1964 - the first operating system to be able to run on multiple different designs of machine.
At this stage programming was still done in machine code, and so operating systems were enormously complicated programs. Debugging was very difficult, both when writing custom programs and when issues arose with an OS.
### Phase 2: Multiple users (1970-1980)
Operating systems at this stage were helping to increase productivity, and allowing multiple users to work one machine. Terminals began to be given to each user, and and file systems start to be developed. 
Two important operating systems emerge in this time. Compatible Time Sharing System (CTSS) is first released by MIT in 1963. It pioneered research on scheduling, but had shortfalls prompting further development. This development came in a collaboration with MIT, Bell Labs, and General Electric with the release of Multics (Multiplexed Information and Computing Service). Multics was the first system to use hierarchical file systems, and treated external devices as files. It was intended to run on a single large system, allowing users to buy computing power like electricity, as this was the prediction for how people would interact with computing systems.
#### UNIX
Frustrated during the development of Multics by its size and complexity, Ken Thompson, Dennis Ritchie, Douglass Mcllroy, and Joe Ossanna of Bell Labs began to develop their own OS. Billed as a single task system, the team coined the name UNIX in 1970, for Uniplexed Information and Computing Service. Originally written in assembly, UNIX was rewritten in C for version 4 in 1973. One key goal was the idea of portability, allowing the system to be installed on any machine.
Universities were given UNIX's codebase for research, and Berkeley added virtual memory support. Then, UNIX became a commercial OS.
UNIX pioneered writing OSes in 'high level' languages (C), making portable OSes, mountable file systems, and more.
## Phase 3: Cheaper hardware (1980-1990)
Thinking began to shift from multi-user systems as hardware became cheaper, and personal computers became feasible. The Control Program/Monitor (CP/M) OS had been in development for around 6 years when IBM realised that it was too far behind schedule to release on their new machines. They approached Bill Gates, who bought and adapted a previous clone of CM/P called 86-DOS that was made by Seattle computer Products to run on 8086 processors. The newly adapted OS was called MS-DOS (Microsoft Disk Operating System), and used the FAT32 file system instead of CM/P's proprietary one while still being able to run CM/P programs. MS-DOS being shipped on IBS machines meant that as IBM advanced their hardware, Microsoft grew in market share and began to outstrip CM/P's popularity. This is the dawn of the current computer age. 
## Phase 4: Networked systems (1990-)
In the modern age, connectivity is of most significance. Networked applications such as email and browsers enable commerce, and users wish to share data quickly between one another. Memory protection and multiprogramming is now less important on individual machines, but has become much more important on servers as cloud storage and computing has gained popularity. Clusters, grids, distributed OSes and the cloud have meant a surge in network-based architectures.
## Phase 5: Something new (????-????)
With the increased prevalence of mobile devices, mobile operating systems, the Internet of Things, many researchers believe that a substantial enough shift has occurred for a new phase of technological development to be defined.
