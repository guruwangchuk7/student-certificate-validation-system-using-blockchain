Professional Requirement Analysis and Development Planning Document
Student Certificate Validation System Using Blockchain
1. Project Title
Student Certificate Validation System Using Blockchain

2. Project Overview
The Student Certificate Validation System Using Blockchain is a blockchain-based decentralized application designed to support the secure issuance, storage, access, and verification of academic certificates. The system enables universities and academic authorities to issue student certificates digitally, allows students to access and share their certificates, and enables employers or verification agencies to instantly confirm the authenticity of certificates without depending on manual institutional verification.
The system will use Ethereum blockchain as the immutable trust layer for certificate validation, while Supabase will be used for user authentication, database management, and certificate file storage. The application will be developed using Scaffold-ETH 2, which provides a modern development framework for Ethereum-based decentralized applications.
The core idea of the system is that the actual certificate file will be stored securely in Supabase Storage, while a unique cryptographic hash of the certificate file will be stored on the Ethereum blockchain. During verification, the uploaded certificate is hashed again and compared with the blockchain record. If the hash matches, the certificate is confirmed as valid. If the hash does not match, the certificate is considered invalid or tampered.
This approach provides a practical, secure, and efficient solution by combining centralized application management through Supabase with decentralized trust and immutability through blockchain.

3. Background and Problem Statement
Academic certificate verification is traditionally a slow and manual process. Employers, institutions, and verification agencies often need to contact universities or academic boards directly to confirm whether a certificate is genuine. This process can take days or weeks and may involve paperwork, emails, phone calls, and administrative delays.
In addition, paper-based or digitally edited certificates are vulnerable to forgery, duplication, and manipulation. A fake certificate can be created or modified using simple editing tools, making it difficult for employers to verify authenticity without official confirmation.
The absence of a reliable, instant, and tamper-proof certificate verification system creates problems for universities, students, and employers. Universities face administrative burdens, students depend on institutions every time they need verification, and employers face uncertainty during recruitment.
The proposed system solves this problem by using blockchain technology to create a permanent and tamper-proof certificate validation record. Once a certificate is issued, its cryptographic hash is stored on the blockchain. Since blockchain records cannot be easily altered or deleted, the system provides a reliable way to verify certificates instantly.

4. Aim of the Project
The aim of the project is to develop a secure blockchain-based student certificate validation system that enables academic institutions to issue certificates, students to access and share their certificates, and employers to verify certificate authenticity instantly using Ethereum blockchain and Supabase.

5. Project Objectives
The main objectives of the system are:
To provide a secure digital platform for issuing student certificates.
To allow universities and academic boards to upload and register certificates digitally.
To store certificate files securely using Supabase Storage.
To generate a unique cryptographic hash for every certificate file.
To store the certificate hash permanently on the Ethereum blockchain.
To allow students to create accounts using their Bhutanese CID as the primary identity reference.
To link issued certificates to students through their CID.
To allow students to view, download, and share their issued certificates.
To allow employers or verifiers to upload a certificate and verify its authenticity instantly.
To reduce certificate forgery, administrative delays, and dependency on manual verification.
To provide a transparent, reliable, and tamper-resistant academic certificate verification mechanism.

6. Scope of the Project
The scope of the project includes the design and development of a blockchain-based certificate validation system for academic certificates in Bhutan. The system will focus on three major stakeholders: universities or academic boards, students, and employers or verifiers.
6.1 Decentralized Application
The system will be developed as a decentralized application using Scaffold-ETH 2. The application will interact with Ethereum smart contracts to store and verify certificate hashes. Although the application uses Supabase for authentication, database management, and file storage, the final certificate authenticity proof will remain on the blockchain.
6.2 Immutable Certificate Proof on Ethereum
The system will store certificate hash values on the Ethereum blockchain. A hash is a unique digital fingerprint of a certificate file. If the certificate file is modified even slightly, the hash will change. By storing the original certificate hash on the blockchain, the system ensures that any tampering can be detected during verification.
6.3 Certificate File Storage Using Supabase
Instead of using IPFS, the system will use Supabase Storage to store certificate files such as PDF or image documents. Supabase provides easier integration with authentication, access control, database records, and dashboard management. The certificate file itself will be stored in Supabase, while its hash will be stored on the blockchain for authenticity verification.
6.4 Student Identity Using Bhutanese CID
Since the system is initially designed for Bhutan, the student’s Citizenship Identity Card number, known as CID, will be used as the primary student identity reference. Students will create accounts using their CID, and when an admin uploads a certificate, the certificate will be linked to the student’s CID.
For security and privacy, the raw CID should not be stored publicly on the blockchain. Instead, a hashed version of the CID should be used for blockchain linkage.
6.5 Instant Certificate Verification
Employers, companies, institutions, and verification agencies will be able to upload a certificate file to the system. The system will generate a hash of the uploaded file and compare it with the hash stored on the blockchain. If the hash matches, the certificate will be shown as valid. If it does not match, the certificate will be shown as invalid or tampered.
6.6 Student Empowerment
Students will have lifelong digital access to their certificates. They will be able to view, download, and share certificate verification links with employers or institutions without repeatedly contacting their university.
6.7 Efficient Data Management
Supabase will be used for fast querying, authentication, role management, student profiles, certificate metadata, verification logs, and dashboard data. This makes the system easier to manage, faster to use, and more practical for development.

7. Stakeholder Analysis
7.1 Universities and Academic Boards
Universities, colleges, and academic boards are responsible for issuing student certificates. In the system, they will act as certificate issuers. They will upload certificates, enter certificate metadata, and register certificate hashes on the blockchain.
Benefits for universities include:
Reduced manual verification workload.
Secure and tamper-proof certificate issuance.
Better record management.
Reduced certificate forgery.
Faster response to employer verification requests.
7.2 Students
Students are the owners of the academic certificates issued to them. They will create their own accounts using CID and will be able to access certificates linked to their identity.
Benefits for students include:
Lifelong access to certificates.
Easy sharing with employers or institutions.
Reduced dependency on university offices.
Improved trust in digital academic credentials.
Ability to download and present certificates anytime.
7.3 Employers and Verifiers
Employers, companies, HR departments, institutions, and verification agencies will use the system to validate certificates submitted by students or job applicants.
Benefits for verifiers include:
Instant verification.
Reduced manual communication with universities.
Better confidence in applicant credentials.
Faster recruitment and admission decisions.
Detection of forged or edited certificates.

8. Proposed Technology Stack
Layer
Technology
Purpose
Frontend / DApp Framework
Scaffold-ETH 2
Build Ethereum-based decentralized application
Blockchain
Ethereum
Store immutable certificate hash and verification records
Smart Contract Language
Solidity
Develop certificate registry smart contract
Authentication
Supabase Auth
Register and authenticate students, admins, and verifiers
Database
Supabase PostgreSQL
Store users, roles, certificate metadata, and logs
File Storage
Supabase Storage
Store certificate PDF/Image files
Wallet Integration
Scaffold-ETH 2 wallet tools
Connect admin blockchain wallet
Hosting
Vercel or similar
Deploy frontend application


9. System Architecture
The system architecture follows a hybrid blockchain model. Supabase is used for application-level data management, while Ethereum is used for immutable certificate proof.
9.1 Architecture Flow
Student / Admin / Verifier
        ↓
Frontend DApp using Scaffold-ETH 2
        ↓
Supabase Auth and Database
        ↓
Supabase Storage for Certificate Files
        ↓
Certificate Hash Generation
        ↓
Ethereum Smart Contract
        ↓
Blockchain Verification Result

9.2 Storage Strategy
Data Type
Storage Location
Reason
Certificate PDF/Image
Supabase Storage
Easy file management and access control
Certificate hash
Ethereum blockchain
Tamper-proof verification proof
Student profile
Supabase Database
Fast access and user management
CID number
Supabase Database, protected
Required for Bhutan-based student identification
CID hash
Blockchain / Supabase
Privacy-preserving identity linkage
Certificate metadata
Supabase Database
Fast dashboard display
Transaction hash
Supabase Database
Reference to blockchain transaction
Verification logs
Supabase Database
Audit and reporting


10. User Roles and Access Control
The system will have three primary user roles.
10.1 Admin / University User
The admin represents the university, college, or academic board. The admin can issue certificates, upload files, and manage issued records.
Admin permissions:
Login to admin dashboard.
Upload certificate PDF/Image files.
Enter student and certificate details.
Link certificate to student CID.
Generate certificate hash.
Store certificate hash on blockchain.
View issued certificates.
Revoke incorrect or cancelled certificates.
10.2 Student User
The student creates an account using CID and accesses certificates linked to their identity.
Student permissions:
Register account.
Login to student dashboard.
View issued certificates linked to CID.
Download certificate file.
Share certificate verification link.
View certificate status.
10.3 Verifier / Employer User
The verifier checks whether a certificate is authentic.
Verifier permissions:
Upload certificate file for validation.
Enter certificate ID or verification link.
View certificate verification result.
View basic certificate details if valid.
Access verification history if logged in.

11. Functional Requirements
11.1 Student Registration and Authentication
Requirement ID
Requirement Description
Priority
FR-01
The system shall allow students to create an account using full name, email, password, and CID number.
High
FR-02
The system shall require CID to be unique for each student account.
High
FR-03
The system shall validate that the CID field is not empty during registration.
High
FR-04
The system shall authenticate students using Supabase Auth.
High
FR-05
The system shall allow students to log in and log out securely.
High
FR-06
The system shall link issued certificates to the student account using CID or CID hash.
High
FR-07
The system shall prevent students from viewing certificates belonging to other students.
High


11.2 Admin Certificate Issuance
Requirement ID
Requirement Description
Priority
FR-08
The system shall allow authorized admins to log in to the admin dashboard.
High
FR-09
The system shall allow admins to upload certificate files in PDF, JPG, or PNG format.
High
FR-10
The system shall store uploaded certificate files in Supabase Storage.
High
FR-11
The system shall generate a unique cryptographic hash of each uploaded certificate file.
High
FR-12
The system shall allow admins to enter student name, CID, degree, program, institution, issue date, and certificate title.
High
FR-13
The system shall link the certificate to the student’s CID.
High
FR-14
The system shall store the certificate hash on Ethereum blockchain through a smart contract.
High
FR-15
The system shall store certificate metadata in Supabase Database for dashboard use.
High
FR-16
The system shall generate a unique certificate ID for every certificate.
High
FR-17
The system shall record the blockchain transaction hash after successful certificate issuance.
High
FR-18
The system shall display issued certificates in the admin dashboard.
Medium


11.3 Student Certificate Management
Requirement ID
Requirement Description
Priority
FR-19
The system shall allow students to view all certificates linked to their CID.
High
FR-20
The system shall display certificate details such as certificate title, degree, issue date, institution, and status.
High
FR-21
The system shall allow students to download certificate files.
Medium
FR-22
The system shall allow students to generate or copy a shareable verification link.
High
FR-23
The system shall allow students to view whether a certificate is valid or revoked.
Medium
FR-24
The system may allow students to generate QR codes for certificate sharing.
Low


11.4 Certificate Verification
Requirement ID
Requirement Description
Priority
FR-25
The system shall allow verifiers to upload a certificate file for validation.
High
FR-26
The system shall generate a hash of the uploaded certificate file.
High
FR-27
The system shall compare the generated hash with the certificate hash stored on blockchain.
High
FR-28
The system shall display verification result as Valid, Invalid, Revoked, or Not Found.
High
FR-29
The system shall display basic certificate information if the certificate is valid.
High
FR-30
The system shall prevent unauthorized users from viewing sensitive student data.
High
FR-31
The system shall record verification attempts in Supabase for audit purposes.
Medium


11.5 Certificate Revocation
Requirement ID
Requirement Description
Priority
FR-32
The system shall allow authorized admins to revoke a certificate.
High
FR-33
The system shall update the certificate status as revoked on the blockchain.
High
FR-34
The system shall update the certificate status in Supabase.
High
FR-35
The system shall display revoked certificates as invalid for verification purposes.
High
FR-36
The system shall not allow admins to permanently delete issued blockchain records.
High


12. Non-Functional Requirements
Category
Requirement Description
Security
The system shall protect student CID and personal information from public exposure.
Privacy
Raw CID shall not be stored directly on blockchain. A hashed CID should be used for blockchain reference.
Performance
Certificate verification should be completed within a few seconds under normal network conditions.
Reliability
The system shall maintain certificate records even if the frontend application is updated.
Scalability
The system shall support multiple institutions and a growing number of certificates.
Usability
The system shall be easy to use for non-technical students, admins, and employers.
Availability
The public verification page should be accessible at all times.
Maintainability
The system should be modular, with separate smart contract, frontend, database, and storage layers.
Auditability
Every certificate issuance and revocation shall be traceable through blockchain transaction hash.
Compatibility
The system should support common certificate formats such as PDF, JPG, and PNG.


13. Smart Contract Requirement Analysis
The Ethereum smart contract will act as the permanent certificate proof registry. It should not store full certificate files or sensitive student information. It should store only essential verification data.
13.1 Suggested Smart Contract Data Fields
Field
Description
certificateId
Unique identifier for each certificate
certificateHash
Hash of the uploaded certificate file
studentCidHash
Hashed version of the student CID
institutionName
Name of issuing institution
issueDate
Date of certificate issuance
issuerAddress
Wallet address of issuing admin/institution
isRevoked
Revocation status

13.2 Suggested Smart Contract Functions
Function
Purpose
issueCertificate
Stores a new certificate hash on blockchain
verifyCertificate
Checks whether a certificate hash exists and is valid
revokeCertificate
Marks a certificate as revoked
getCertificate
Returns certificate verification details
addIssuer
Adds an authorized certificate issuer
removeIssuer
Removes an authorized certificate issuer

13.3 Smart Contract Events
Event
Purpose
CertificateIssued
Triggered when a new certificate is issued
CertificateRevoked
Triggered when a certificate is revoked
IssuerAdded
Triggered when a new issuing authority is added
IssuerRemoved
Triggered when an issuing authority is removed


14. Database Requirement Analysis
Supabase PostgreSQL will be used for application-level data management. The database will support user profiles, role management, certificate metadata, storage references, and verification logs.
14.1 Table: profiles
Column
Type
Description
id
uuid
Supabase authentication user ID
full_name
text
Full name of user
email
text
User email address
role
text
student, admin, or verifier
cid_number
text
Student CID, protected in database
cid_hash
text
Hashed CID for matching
created_at
timestamp
Account creation date

14.2 Table: institutions
Column
Type
Description
id
uuid
Institution ID
institution_name
text
Name of university, college, or board
institution_type
text
University, college, board, or training institute
wallet_address
text
Authorized Ethereum wallet address
is_verified
boolean
Institution approval status
created_at
timestamp
Record creation date

14.3 Table: certificates
Column
Type
Description
id
uuid
Database certificate record ID
certificate_id
text
Public certificate identifier
student_cid_hash
text
Hashed student CID
student_name
text
Student name
certificate_title
text
Title of certificate
degree_program
text
Degree or academic program
institution_id
uuid
Issuing institution reference
file_url
text
Supabase Storage file URL/path
certificate_hash
text
Hash of certificate file
blockchain_tx_hash
text
Blockchain transaction hash
status
text
valid, revoked, pending, or failed
issued_at
date
Certificate issue date
created_at
timestamp
System record date

14.4 Table: verification_logs
Column
Type
Description
id
uuid
Verification log ID
certificate_id
text
Certificate checked
verifier_email
text
Email of verifier, if logged in
uploaded_file_hash
text
Hash of uploaded verification file
result
text
Valid, Invalid, Revoked, or Not Found
checked_at
timestamp
Verification date and time


15. Main System Modules
15.1 Authentication Module
This module handles user registration, login, logout, and role-based access. Supabase Auth will be used for authentication.
Main features:
Student registration.
Admin login.
Verifier login, if required.
Role-based dashboard redirection.
Session management.
15.2 Certificate Issuance Module
This module allows admins to upload and issue certificates.
Main features:
Upload certificate file.
Enter student CID and certificate details.
Generate certificate hash.
Store file in Supabase Storage.
Store certificate hash on blockchain.
Save metadata in Supabase Database.
15.3 Student Dashboard Module
This module allows students to view and manage their own certificates.
Main features:
View issued certificates.
View certificate status.
Download certificate file.
Copy shareable verification link.
View blockchain transaction reference.
15.4 Verification Module
This module allows employers or verifiers to validate certificates.
Main features:
Upload certificate file.
Generate uploaded file hash.
Compare hash with blockchain record.
Display verification result.
Show valid certificate details.
Store verification log.
15.5 Revocation Module
This module allows admins to revoke wrong, cancelled, or invalid certificates.
Main features:
Select issued certificate.
Provide revocation reason.
Update blockchain status.
Update Supabase status.
Show revoked status during verification.

16. User Flow Analysis
16.1 Student Registration Flow
Student opens the platform
→ Student clicks Register
→ Student enters name, email, password, and CID
→ System validates CID uniqueness
→ System creates Supabase Auth account
→ System creates student profile
→ Student logs in
→ Student dashboard displays certificates linked to CID

16.2 Certificate Issuance Flow
Admin logs in
→ Admin opens Issue Certificate page
→ Admin enters student CID and certificate details
→ Admin uploads certificate PDF/Image
→ System stores file in Supabase Storage
→ System generates certificate hash
→ System sends hash to Ethereum smart contract
→ Blockchain transaction is completed
→ Transaction hash is saved in Supabase
→ Certificate appears in student dashboard

16.3 Certificate Verification Flow
Verifier opens Verify Certificate page
→ Verifier uploads certificate file
→ System generates hash of uploaded file
→ System checks hash against Ethereum smart contract
→ System checks revocation status
→ System displays result as Valid, Invalid, Revoked, or Not Found
→ Verification log is saved in Supabase

16.4 Certificate Sharing Flow
Student logs in
→ Student opens certificate details
→ Student copies verification link
→ Student shares link with employer
→ Employer opens link
→ System displays certificate authenticity status


17. Certificate Verification Status
Status
Meaning
Valid
Certificate hash matches blockchain record and is not revoked
Invalid
Uploaded file hash does not match any blockchain record
Revoked
Certificate exists but has been revoked by the issuing authority
Not Found
No matching certificate record exists
Pending
Certificate upload started but blockchain transaction is not completed


18. Recommended Pages and Screens
18.1 Public Pages
Page
Description
Home Page
Introduces the system and explains benefits
Verify Certificate Page
Allows certificate upload or certificate ID verification
Public Certificate View
Displays certificate authenticity result
Login Page
Allows users to access their dashboard
Register Page
Allows students to create account

18.2 Admin Dashboard Pages
Page
Description
Admin Overview
Shows total certificates issued, verified, and revoked
Issue Certificate
Allows admin to upload and register a certificate
Issued Certificates
Shows list of issued certificates
Certificate Details
Shows full details of a selected certificate
Revoke Certificate
Allows admin to revoke a certificate
Institution Profile
Shows university or board details

18.3 Student Dashboard Pages
Page
Description
My Certificates
Shows certificates linked to student CID
Certificate Details
Shows certificate metadata and status
Download Certificate
Allows student to download certificate file
Share Certificate
Provides shareable verification link
Student Profile
Shows student account information

18.4 Verifier Pages
Page
Description
Verify Upload
Allows file upload for validation
Verification Result
Displays valid, invalid, revoked, or not found result
Verification History
Optional page for logged-in companies


19. Security and Privacy Considerations
The system handles sensitive student information, especially CID numbers. Therefore, security and privacy must be considered carefully.
Important security requirements:
CID numbers should not be stored directly on the blockchain.
CID numbers should be protected in Supabase using access policies.
Hashed CID should be used for blockchain matching.
Only authorized admin wallets should be able to issue certificates.
Students should only view certificates linked to their own CID.
Verifiers should only see basic certificate information.
Supabase Row Level Security should be enabled.
Certificate files should not be publicly editable.
Blockchain should be treated as the final trust source.
Revoked certificates should remain visible as revoked, not deleted.

20. Testing Plan
20.1 Test Case TC01: Admin Uploads a New Certificate
Field
Description
Test Case ID
TC01
Test Case Name
Admin uploads a new certificate
Actor
Admin / University
Precondition
Admin is logged in and authorized
Input
Student CID, certificate details, certificate PDF/Image
Process
Upload file, generate hash, store file, record hash on blockchain
Expected Result
Certificate is successfully issued and linked to student CID
Output
Certificate status: Valid

20.2 Test Case TC02: Student Views Certificate
Field
Description
Test Case ID
TC02
Test Case Name
Student views issued certificate
Actor
Student
Precondition
Student account exists and certificate is linked to CID
Input
Student login credentials
Process
Student logs in and opens dashboard
Expected Result
Student can view certificate details
Output
Certificate displayed with download and share options

20.3 Test Case TC03: Verifier Uploads Certificate for Validation
Field
Description
Test Case ID
TC03
Test Case Name
Verifier uploads certificate for validation
Actor
Employer / Verifier
Precondition
Certificate has already been issued
Input
Certificate PDF/Image
Process
Upload file, generate hash, compare with blockchain record
Expected Result
System displays whether certificate is valid or invalid
Output
Verification result shown to verifier

20.4 Additional Test Cases
Test Case ID
Test Scenario
Expected Result
TC04
Student registers with duplicate CID
System rejects duplicate CID
TC05
Admin uploads unsupported file type
System rejects file
TC06
Verifier uploads tampered certificate
System displays Invalid
TC07
Admin revokes certificate
Certificate status becomes Revoked
TC08
Verifier checks revoked certificate
System displays Revoked
TC09
Unauthorized wallet tries to issue certificate
Transaction is rejected
TC10
Student tries to access another student’s certificate
Access is denied
TC11
Admin submits incomplete certificate details
System shows validation error
TC12
Blockchain transaction fails
Certificate status remains Pending or Failed


21. Development Roadmap
Phase 1: Requirement Finalization
Tasks:
Finalize user roles.
Finalize certificate data fields.
Finalize verification process.
Finalize database schema.
Finalize smart contract structure.
Prepare wireframes for main screens.
Deliverables:
Requirement document.
Database design.
Smart contract design.
UI screen plan.
Phase 2: Smart Contract Development
Tasks:
Develop certificate registry smart contract.
Add authorized issuer control.
Add certificate issue function.
Add certificate verify function.
Add certificate revoke function.
Write smart contract tests.
Deliverables:
Solidity smart contract.
Contract test cases.
Deployed testnet contract.
Phase 3: Supabase Backend Setup
Tasks:
Set up Supabase project.
Configure authentication.
Create database tables.
Configure storage bucket.
Set role-based access policies.
Create verification logs table.
Deliverables:
Supabase database schema.
Supabase storage setup.
Authentication and access control policies.
Phase 4: Frontend Development with Scaffold-ETH 2
Tasks:
Set up Scaffold-ETH 2 project.
Build landing page.
Build login and registration pages.
Build admin dashboard.
Build student dashboard.
Build verifier page.
Integrate wallet connection.
Integrate smart contract calls.
Deliverables:
Functional frontend DApp.
Role-based dashboards.
Blockchain interaction features.
Phase 5: Certificate Upload and Verification Integration
Tasks:
Implement file upload to Supabase Storage.
Generate certificate hash on upload.
Send hash to smart contract.
Save transaction hash in Supabase.
Implement verifier upload and hash comparison.
Display verification result.
Deliverables:
Working certificate upload flow.
Working blockchain registration flow.
Working verification flow.
Phase 6: Testing and Quality Assurance
Tasks:
Test student registration.
Test certificate issuance.
Test certificate verification.
Test tampered certificate detection.
Test revoked certificate flow.
Test role-based access.
Test database security policies.
Deliverables:
Test report.
Bug fixes.
Final stable version.
Phase 7: Deployment and Demonstration
Tasks:
Deploy smart contract on Ethereum testnet.
Deploy frontend on Vercel or similar hosting.
Configure Supabase production environment.
Prepare demo data.
Prepare final presentation and documentation.
Deliverables:
Deployed application.
Demo certificate records.
Final project report.
Presentation slides.

22. Minimum Viable Product Scope
For the first version, the system should focus on the essential features required to demonstrate the concept.
Feature
Include in MVP
Student registration using CID
Yes
Supabase authentication
Yes
Admin certificate upload
Yes
Certificate file storage in Supabase
Yes
Certificate hash generation
Yes
Store certificate hash on Ethereum
Yes
Student certificate dashboard
Yes
Verifier file upload
Yes
Blockchain verification result
Yes
Certificate revocation
Yes
QR code generation
Optional
Multi-institution management
Basic only
Advanced analytics
No
Payment system
No


23. Risk Analysis
Risk
Impact
Mitigation
Blockchain transaction cost
Medium
Use Ethereum testnet for academic demo and optimize contract storage
CID privacy exposure
High
Store hashed CID on blockchain instead of raw CID
Supabase file access misconfiguration
High
Apply strict storage and database policies
Admin wallet compromise
High
Restrict issuer permissions and allow issuer removal
User confusion with blockchain wallets
Medium
Keep wallet interaction mainly for admins
File tampering
Low
Detect using certificate hash comparison
Network delay during blockchain transaction
Medium
Use pending transaction status and clear loading messages
Duplicate certificate issue
Medium
Prevent duplicate certificate hash or certificate ID


24. Professional Recommendation
For this project, using Supabase Storage instead of IPFS is acceptable and practical, especially for a student project or prototype. IPFS is useful for decentralized file storage, but it adds additional development complexity. Since the system already uses Ethereum blockchain for immutable certificate proof, Supabase can safely handle file storage as long as the certificate hash is stored on-chain.
The most important rule is that the blockchain should store the certificate hash, not just database information. The certificate hash is the evidence that proves whether the uploaded certificate is original or tampered.
The recommended final architecture is:
Supabase Auth = user login and role management
Supabase Database = student, certificate, institution, and verification records
Supabase Storage = certificate file storage
Ethereum Blockchain = immutable certificate hash and status
Scaffold-ETH 2 = frontend and smart contract interaction framework

This architecture is easier to build, easier to demonstrate, and technically strong enough for a blockchain-based certificate validation system.

25. Final Requirement Statement
The Student Certificate Validation System Using Blockchain shall provide a secure digital platform for issuing, accessing, sharing, and verifying academic certificates. Students shall create accounts using their Bhutanese CID as the primary identity reference, while universities and academic boards shall upload certificates and link them to the student CID. Certificate files shall be stored securely in Supabase Storage, and a cryptographic hash of each certificate shall be stored permanently on the Ethereum blockchain. Employers and verifiers shall be able to upload a certificate file, after which the system shall generate a hash and compare it with the blockchain record to determine whether the certificate is valid, invalid, revoked, or not found. Supabase shall support authentication, database management, file storage, and user dashboards, while Ethereum shall provide the immutable trust layer for certificate authenticity.

26. Conclusion
The proposed Student Certificate Validation System Using Blockchain provides a secure, efficient, and transparent solution for academic certificate verification. By combining Ethereum blockchain with Supabase and Scaffold-ETH 2, the system achieves a practical balance between decentralization, usability, performance, and security.
The system reduces the risk of certificate forgery, eliminates unnecessary manual verification processes, and gives students lifelong digital access to their academic credentials. It also helps employers and institutions verify academic records quickly and confidently.
For Bhutan, using CID as the primary student identity reference makes the system locally relevant and practical. However, privacy must be carefully protected by avoiding direct exposure of CID on the blockchain. With proper hashing, role-based access control, and secure smart contract design, the system can become a reliable academic credential validation platform.

