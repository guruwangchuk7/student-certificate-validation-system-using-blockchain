flowchart TD

    A([Start]) --> B[User Opens Student Certificate Validation System]

    B --> C{Select User Type / Route}

    C --> D[Student]
    C --> E[Admin / University]
    C --> F[Verifier / Employer]
    C --> G[Hidden Super Admin Route: /appointadmin]

    %% SUPER ADMIN / APPOINT ADMIN FLOW
    G --> G1[Super Admin Logs In]
    G1 --> G2[System Checks Super Admin Authorization]
    G2 --> G3{Authorized Super Admin?}

    G3 -->|No| G4[Access Denied]
    G4 --> Z([End])

    G3 -->|Yes| G5[Open Appoint Admin Dashboard]
    G5 --> G6[Select Registered User]
    G6 --> G7[Select Institution / University]
    G7 --> G8[Enter or Confirm Admin Wallet Address]
    G8 --> G9[Create Admin Appointment Record in Supabase]
    G9 --> G10[Update User Role to Admin]
    G10 --> G11[Link Admin to Institution]
    G11 --> G12[Admin Can Now Issue Certificates]
    G12 --> Z

    %% STUDENT FLOW
    D --> D1[Student Registers / Logs In]
    D1 --> D2[Enter Name, Email, Password and CID]
    D2 --> D3[Supabase Auth Validates User]
    D3 --> D4{CID Already Registered?}

    D4 -->|Yes| D5[Show Duplicate CID Error]
    D5 --> Z

    D4 -->|No| D6[CID is Stored Securely in Supabase]
    D6 --> D7[CID Hash is Generated]
    D7 --> D8[Student Profile Created]
    D8 --> D9[Student Dashboard Opens]
    D9 --> D10[View Certificates Linked to CID]
    D10 --> D11[Download Certificate]
    D10 --> D12[Share Verification Link]
    D12 --> Z

    %% ADMIN FLOW
    E --> E1[Admin Logs In]
    E1 --> E2[Supabase Checks Admin Role]
    E2 --> E3[System Checks Wallet Authorization]
    E3 --> E4{Authorized Admin?}

    E4 -->|No| E5[Access Denied]
    E5 --> Z

    E4 -->|Yes| E6[Open Admin Dashboard]
    E6 --> E7[Open Issue Certificate Page]
    E7 --> E8[Enter Student CID and Certificate Details]
    E8 --> E9{Student CID Exists?}

    E9 -->|No| E10[Show Student Not Found / Ask Student to Register]
    E10 --> Z

    E9 -->|Yes| E11[Upload Certificate PDF / Image]
    E11 --> E12{Valid File Type?}

    E12 -->|No| E13[Reject File Upload]
    E13 --> Z

    E12 -->|Yes| E14[Store Certificate File in Supabase Storage]
    E14 --> E15[Generate Certificate Hash]
    E15 --> E16[Send Certificate Hash to Ethereum Smart Contract]
    E16 --> E17{Blockchain Transaction Successful?}

    E17 -->|No| E18[Set Certificate Status as Pending / Failed]
    E18 --> E19[Save Failed Transaction Record in Supabase]
    E19 --> Z

    E17 -->|Yes| E20[Blockchain Stores Immutable Certificate Proof]
    E20 --> E21[Return Blockchain Transaction Hash]
    E21 --> E22[Save Metadata and Transaction Hash in Supabase Database]
    E22 --> E23[Certificate Status Set as Valid]
    E23 --> E24[Certificate Appears in Student Dashboard]
    E24 --> Z

    %% CERTIFICATE REVOCATION FLOW
    E6 --> R1[Open Issued Certificates]
    R1 --> R2[Select Certificate to Revoke]
    R2 --> R3[Enter Revocation Reason]
    R3 --> R4[Send Revoke Request to Ethereum Smart Contract]
    R4 --> R5{Revocation Successful?}

    R5 -->|No| R6[Show Revocation Failed]
    R6 --> Z

    R5 -->|Yes| R7[Update Blockchain Status as Revoked]
    R7 --> R8[Update Supabase Certificate Status]
    R8 --> R9[Save Revocation Log]
    R9 --> Z

    %% VERIFIER FLOW
    F --> F1[Verifier Opens Verification Page]
    F1 --> F2[Upload Certificate File or Enter Certificate ID]
    F2 --> F3[System Generates Hash of Uploaded Certificate]
    F3 --> F4[Check Certificate Hash Against Ethereum Blockchain]
    F4 --> F5{Hash Found on Blockchain?}

    F5 -->|No| F6[Display Result: Invalid / Not Found]
    F6 --> F11[Save Verification Log in Supabase]
    F11 --> Z

    F5 -->|Yes| F7{Certificate Revoked?}

    F7 -->|Yes| F8[Display Result: Revoked]
    F8 --> F11

    F7 -->|No| F9[Display Result: Valid]
    F9 --> F10[Show Basic Certificate Details]
    F10 --> F11