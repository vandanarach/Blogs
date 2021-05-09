# **Active Directory Concepts**

## **Overview:**

	• Active Directory concepts are important for ethical hacking 
	• Like a phone book: Stores all kinds of info and these info can be called objects - such as computers, users and printers 
	• Printers and Linux machines, firewalls, non-windows machines etc can authenticate to AD via Radius and LDAP. 
	• Authentication on windows based devices using AD uses Kerberos tickets 
	• Commonly used identity management service in the world. 
	• 95% of the Fortune 1000 companies use AD 
	• Can be exploitable without ever attacking patchable exploits - we can abuse features, trusts, components and more.

## **Physical Components of AD:**

### _1) Domain controller:_

	• DC hosts the AD Domains Services Data store
	• Provides authentication and authorization services 
	• Replicates updates to other DCs in the domain and forest 
	• Allows administrative access to manage user accounts and network resources

### _2) AD DS data store:_ 

	• The AD DS data store contains the database files and processes that store and manage directory info for users, services and applications 
	• Contains the "Ntds.dit" file, this file is stored by default in the %SystemRoot%\NTDS folder on all DCs 
	• Is accessible only through the DC processes and protocols 
	• This file is very sensitive. It contains all the AD information users, groups etc and more importantly password hashes

## **Logical Components of AD are:**

### _1) AD DS Schema:_

	• Rule book or blueprint definitions of every type of object that can be created in AD 
	• Enforces rules about regarding object creation and configuration. 
	• Object types are: 
		○ Class Object : What objects that can be created in the directory: eg user, computer 
		○ Attribute Object: Info that can be attached to an object: eg: display name etc

### _2) Domains:_

	• Used to group and manage objects in an organization 
	• An administrative boundary for applying policies to groups of objects 
	• A replication boundary to replicate data between domain controllers 
	• An authentication and authorization boundary that provides a way to limit the scope of access to resources

### _3) Trees:_

	• Hierarchy of domains in AD DS 
	• All domains in the tree: 
		○ Share a contiguous namespace with the parent domain 
		○ Can have additional child domains 
		○ By default create a two-way transitive trust with other domains

### _4) Forests: A collection of one or more domain trees_

	• Share a common schema 
	• Share a common config partition 
	• Share a common global catalogue to enable searching 
	• Enable trust between all domains in a forest 
	• Share the enterprise admins and the schema admins groups

### _5) OUs: Organizational units are AD containers that contain users, groups, computers and other OUs_

	• OUs are used to: Represent your org hierarchically and logically 
	• Manage a collection of objects in a consistent way 
	• Delegate permissions to administer group of objects Apply policies

### _6) Trusts: provide a mechanism for users to gain access to resources in another domain_ 

	• Types of trust: 
		○ 1) Directional: The trust direction flows from the trusting domain to the trusted domain 
		○ 2) Transitive: The trust relationship is extended beyond a 2-domain trust to include the other trusted domains
	• All domains in a forest trust all other domains in the forest 
	• Trusts can extend outside the forest also called as cross-domains

### _7) Objects:_

	Examples: 
	• Users- Enables network resource access for a user, 
	• InetOrgPerson - similar to a user account, used for compatibility with other directory services, 
	• Contacts - Used primarily to assign email addresses to external users, does not enable nw access, 
	• Groups - Used to simplify the administration of access control, 
	• Computers - Enables authentication and auditing of computer access to resources,
	• Printers - Used to simplify the process of locating and connecting to printers
	
## Some key takeaways!

	• Grouping of objects == Domains 
	• Multiple domains == trees 
	• Multiple trees == forest 
	• OUs == consist of objects == all the elements of the domains
