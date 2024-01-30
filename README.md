## Developing a Blockchain-Based eVault for Legal Records
The objective of this project is to develop a blockchain-based eVault system for legal records that can ensure security, transparency, and accessibility for all stakeholders.
The system should be able to store, manage, and share legal records securely and efficiently.


## Requirements: 
1. The eVault system is based on a blockchain platform Hyperledger Fabric: A permissioned blockchain framework supporting modular architecture and private channels for confidentiality.
2. The system has user-friendly interfaces for lawyers, judges,and, clients to interact with the eVault, with features such as uploading and retrieving documents, tracking changes, and sharing information.
3. The system  ensures the privacy and confidentiality of legal records.

   
## Expected Outcomes: 
A functional prototype of the blockchain-based eVault system for legal records, with a user-friendly interface and features such as document upload, retrieval, and sharing.
A detailed design document outlining the architecture, features, and technical specifications of the eVault system.


## Impact: 
The development of a blockchain-based eVault system for legal records can have a significant impact on improving access to justice in India. It can lead to faster, more efficient court proceedings, reduced costs, and increased trust in the justice system. Moreover, it can provide a secure and transparent platform for storing and sharing legal records, making it easier for clients to access their own records and for lawyers to access relevant case information.

## PROJECT
UI file:
[Click me](https://www.figma.com/file/Spmi4HuCpkWGHYp3uqR7LU/Workflow?type=whiteboard&node-id=0%3A1&t=Kak22lYKaQsy21cl-1)


WorkFlow Progress:

## Why Hyperledger Fabric?
Hyperledger stands out due to its modular architecture, providng greater flexibility and customisation options. It incorparates security features such as permissioned access, encryption, and authentication mechanisms. It allows you to create a private and permissioned blockchain network which is beneficial for legal records, as it enables fine-grained control over who can participate and access data.

The Linux Foundaton hosts this global collaboration, which comprises professionals in finance, banking, the IOT, supply chains, manufacturing and technology.  

![alt text](https://hyperledger-fabric.readthedocs.io/en/release-2.5/_images/hyperledger_fabric_logo_color.png)



![goalsofhyperledger](https://github.com/Team-Tanzanite-KMIT/project-info-docs/assets/138752385/7c70a722-3601-4eef-a321-d05d03452adf)

## Strengths:
1. Permissioned network design suitable for private legal records
2. Modular and flexible architecture for customising components.
3. Support for various consensus mechanisms.
4. Strong focus on enterprise use cases and integration.
5. Chain code using various programming languages

## Considerations:

• Requires a good understanding of blockchain concepts and enterprisearchitecture.

• Might require more development effort compared to public blockchains.

• May have a steeper learning curve for newcomers.



## Layers of HyperLedger:

![layersofhyperledger](https://github.com/Team-Tanzanite-KMIT/project-info-docs/assets/138752385/341f31f0-3334-4a5d-a9ad-d01dcfa34401)




## Organizational structure of hyperledger technology:


API (Application
Programming Interface ), SDK(Software Development Kit) , CLI(Command
Line Interface)


API includes
membership services such as a set of cryptographic certificates,
signifies that peer belongs to the same organisation and
communication between peers f same membership services.


SDK includes
blockchain and transaction layer which constitutes the core code of
the blockchain, consist of consensus algorithm and peer-to-peer
protocol.


CLI includes
membership services which consists of chaincode and logic to run in
operaton on the hyperledger.



Chaincode in Hyperledger is used for smart contracts that defines the logic of decentralised applications running on it. 
## Understanding chaincode:


![chaincode](https://github.com/Team-Tanzanite-KMIT/project-info-docs/assets/138752385/398e226c-9aff-4935-90d3-7fa27ccfcadb)


## Testing and Running the chaincode
## <ins>SUCCESSFUL HALT AND REMOVAL OF HYPERLEDGER FABRIC NETWORK	</ins>





![Screenshot from 2024-01-27 22-48-44](https://github.com/Team-Tanzanite-KMIT/project-info-docs/assets/138752385/4804e9b8-dbdb-4d65-b3e7-2b87fd607cd6)



Hyperledger Fabric Network using Docker and Docker Compose. The key
points are:


1. Containers
Removed:


‘cli’ ,
‘peer0.org2.example.com’ , ‘peer0.org1.example.com’, couchdb0
. Couchdb0, orderer.example.com, ca_orderer, ca_org2


2. Networks Removed:


fabric_test and
compose_default (with warning which was not found)


3. Volume Removed:


compose_orderer.example.com,
compose_orderer2.exmaple.com,compose_peer0.org1.exmaple.com,etc


4. Error Messages:


Error:
Network compose_default not found


Error
response from daemon : get docker_orderer.example.com: no such volume


5.Deleted Generated Chaincode Docker Images:


Images
related to ‘peer0.org2.example.com-filebasic_1.0.1’ were untagged
and deleted.








## <ins> CREATION OF HYPERLEDGER FABRIC NETWORK USING DOCKER AND DOCKER COMPOSE AND SETUP THE INITIAL CONFIGURATION AND IDENTITIES FOR Org1 </ins>





                                                      
![Screenshot from 2024-01-27 23-03-01](https://github.com/Team-Tanzanite-KMIT/project-info-docs/assets/138752385/445efe45-d483-43a7-9a75-95a37175aa53)






1. Objective: Creating a channel named 'mychannel', and Bringing up a Hyperledger Fabric network using Docker and Docker Compose.

   
2.Versions Used:
LOCAL_VERSION: v2.5.4
DOCKER_IMAGE_VERSION: v2.5.4
CA_LOCAL_VERSION v1.5.7
CA_DOCKER_IMAGE_VERSION: v1.5.7


3.CertificateGeneration Using Fabric CA:
Creation of a network named "fabric_test." and Creation of Certificate Authorities (CAs) for orderer, org1, and org2.


4.Organization Identity Setup (Org1): Enrolling the CA admin for org1, Registering peer0 with its credentials (peer0pw), Registering a user named user1 with credentials (user1pw), and Registering the organization admin (org1admin) with credentials (org1adminpw).


5.Generating Peer MSP for peer0 in Org1:Enrolling peer0 with its credentials and generating the MSP (Membership Service Provider) for the peer.


6.Additional Actions: Similar actions are expected for other organizations and peers in the network (Org2).


7. Certificates and Keys: Certificates and keys are stored in specified locations for various entities (admin, user, peer).







	
	
	
	


## <ins> GENERATION OF TLS CERTIFICATES FOR ‘peer0’ IN Org1 AND THE ASSOCIATED USER AND ADMIN IDENTITIES </ins>






![Screenshot from 2024-01-27 23-16-13](https://github.com/Team-Tanzanite-KMIT/project-info-docs/assets/138752385/e07103bd-8d63-4b1c-a554-27388e04cfed)





	
	
	
	


1.  TLS Certificate Generation for peer0 in Org1:
    Command: fabric-ca-client enroll
    URL: https://peer0:peer0pw@localhost:7054
    CA Name: ca-org1
    Output:
        TLS client certificate stored at /home/patelkiran18/Desktop/fabric-samples/test-network/organizations/peerOrganizations/org1.example.com/peers/peer0.org1.example.com/tls/signcerts/cert.pem
        TLS root CA certificate stored at /home/patelkiran18/Desktop/fabric-samples/test-network/organizations/peerOrganizations/org1.example.com/peers/peer0.org1.example.com/tls/tlscacerts/tls-localhost-7054-ca-org1.pem

2. User Identity Generation:
    Command: fabric-ca-client enroll
    URL: https://user1:user1pw@localhost:7054
    CA Name: ca-org1
    Output:
        User certificate stored at /home/patelkiran18/Desktop/fabric-samples/test-network/organizations/peerOrganizations/org1.example.com/users/User1@org1.example.com/msp/signcerts/cert.pem
        Root CA certificate stored at /home/patelkiran18/Desktop/fabric-samples/test-network/organizations/peerOrganizations/org1.example.com/users/User1@org1.example.com/msp/cacerts/localhost-7054-ca-org1.pem

3. Admin Identity Generation:
    Command: fabric-ca-client enroll
    URL: https://org1admin:org1adminpw@localhost:7054
    CA Name: ca-org1



    Output:
        Admin certificate stored at /home/patelkiran18/Desktop/fabric-samples/test-network/organizations/peerOrganizations/org1.example.com/users/Admin@org1.example.com/msp/signcerts/cert.pem
        Root CA certificate stored at /home/patelkiran18/Desktop/fabric-samples/test-network/organizations/peerOrganizations/org1.example.com/users/Admin@org1.example.com/msp/cacerts/localhost-7054-ca-org1.pem

SIMILARLY
FOR Org2........

















## <ins> CREATION OF ORDERER Org IDENTITIES </ins>



1. Generating User MSP for User1 in Org2: Enrolling ‘User1’ with its
credentials and generating the MSP (Membership Service Provider) for
the user and generating certificates and keys.


2. Generating Org Admin Msp for Org2: Enrolling the organization admin
gor Org2 (‘Admin@org2.example.com’)
with its credentials, generation of MSP for the organisation admin
and storage of certificates and keys.


3.Creating Orderer Org Identities: Enrolling the CA admin for the
Orderer Org with its credentials and generation of TLS-enabled
certificates for ordered-related entities.


4. Registering Orderer and Orderer Admin: Registration of orderer with its credentials (ordererpw) as a type orderer, Registration of the orderer admin (ordererAdmin) with credentials (ordererAdminpw) as a type admin.


5.Generating Orderer MSP: Enrolling orderer with its credentials and generating the MSP for the orderer and Storage of certificates and keys.


6.Generating Orderer TLS Certificates: Enrolling orderer with its credentials and generating TLS certificates for the orderer with specified Subject Alternative Names.



	


## <ins> CREATED: DOCKER CONTAINERS FOR HYPERLEDGER FABRIC NETWORK 	</ins>


![Screenshot from 2024-01-27 23-33-05](https://github.com/Team-Tanzanite-KMIT/project-info-docs/assets/138752385/82eae2f1-2a49-4033-889f-65a55f52efa9)




Containers
are created, container status is running and exposed ports. 





	
	
	
	


 ## <ins> CREATED A CHANNEL NAMED ‘mychannel’ AND JOINED THE ORGANISATIONS SETTINGANCHOR PEERS </ins>



Channel
Creation: Created
a channel named mychannel
using the scripts/orderer.sh
script.



Joining
Peers: Joined
the Org1 peer to the channel using the peer
channel join
command and  Joined
the Org2 peer to the channel using the peer
channel join
command.



Setting
Anchor Peers: For
Org1: Fetched the channel configuration, modified it to include the
anchor peer information, and submitted the anchor peer update
transaction to set the anchor peer for Org1, and
For Org2: The process is
presumably similar, but the provided output does not show the
details.








<ins> SUCCESSFUL INSTALLATION OF CHAINCODE ON BOTH ‘peer0.org1’ and ‘peer0.org2’ </ins> 


The
chaincode is packaged using peer lifecycle chaincode package command.


The package is then installed
on peer0.org1
using peer
lifecycle chaincode install
command.


The same package is installed
on peer0.org2
using the same command.





![Screenshot from 2024-01-27 23-40-46](https://github.com/Team-Tanzanite-KMIT/project-info-docs/assets/138752385/99145697-c1bb-4186-b407-010922b130ea)






	
	
	
	


 ## <ins> APPROVE CHAINCODE ,COMMIT CHAINCODE, QUERY AND INVOKE CHAINCODE </ins>


Both
the organisations have approved the chaincode definition and now
chaincode is committed. The approval process involves submitting an
approval request for the chaincode definition, and each organisation
needs to approve it.


Approved
the chaincode definitin for ‘Org1’ using ‘peer lifestyle
chaincode approveformyorg’ , checked the commit readliness for
‘Org1’ using ‘peer lifestyle chaincode checkcommitreadiness’
and approved the chaincode definition for ‘Org2‘ and checked the
commit readiness.


It has
committed the chaincode definition using ‘peer lifecycle chaincode
commit’


Queried
the committed chaincode definition on both ‘peer0.org1’ and
;peer0.org2’ using ‘peer lifestyle chaincode
querycommitted’



Finally, Invoke successfullly the
chaincode definition resulting a indication of status 200.


![Screenshot from 2024-01-27 23-49-31](https://github.com/Team-Tanzanite-KMIT/project-info-docs/assets/138752385/9c308295-5a97-4b98-8a01-d8cc1a34118b)





Chaincode
with version 1.0.1, sequence 1, and endorsement and validation
plugins (escc and vscc) was successfully installed, approved,
committed, and queried on both peers from Org1 and Org2.

