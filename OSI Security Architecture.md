The Open Systems Interconnection (OSI) Security Architecture defines a systematic approach to providing security in a system. It defines categories for attacks, security defences, and abstract layers on which attacks and defence strategies can act, amongst others. 

At the highest level, the OSI architecture is broken down into 3 categories: Security attacks, security mechanisms, and security services.

# Security attacks
Security attacks are any attempts by people or entities to gain unauthorised access to a system. They are subdivided into 2 categories:
- Passive attacks
	Attacks in which a person or entity tries to access information about / stored within the system without authorisation
	Examples include eavesdropping and traffic analysis
- Active attacks
	Attacks in which a person or entity attempts to disrupt or alter the system. 
	Examples include masquerade, replay, message modification, and denial of service

# Security mechanisms
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
	Any mechanism that enforce access rights to resources in the system,

# Security services
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

#cybersecurity