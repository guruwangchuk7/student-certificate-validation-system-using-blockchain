erDiagram

    USERS {
        uuid id PK
        string full_name
        string email UK
        string password_hash
        string role
        string cid_number UK
        string cid_hash UK
        timestamp created_at
        timestamp updated_at
    }

    INSTITUTIONS {
        uuid id PK
        string institution_name
        string institution_type
        string registration_no
        string wallet_address UK
        boolean is_verified
        timestamp created_at
        timestamp updated_at
    }

    ADMIN_APPOINTMENTS {
        uuid id PK
        uuid appointed_user_id FK
        uuid institution_id FK
        string appointed_by_wallet
        string admin_wallet_address UK
        string appointment_status
        timestamp appointed_at
        timestamp revoked_at
    }

    CERTIFICATES {
        uuid id PK
        string certificate_id UK
        uuid student_id FK
        uuid institution_id FK
        uuid issued_by_admin_id FK
        string student_cid_hash
        string student_name
        string certificate_title
        string degree_program
        date issued_at
        string file_url
        string file_path
        string certificate_hash UK
        string blockchain_tx_hash
        string smart_contract_certificate_id
        string status
        timestamp created_at
        timestamp updated_at
    }

    BLOCKCHAIN_RECORDS {
        uuid id PK
        uuid certificate_id FK
        string certificate_hash UK
        string student_cid_hash
        string issuer_wallet_address
        string blockchain_tx_hash UK
        string smart_contract_address
        string network_name
        boolean is_revoked
        timestamp recorded_at
        timestamp revoked_at
    }

    VERIFICATION_LOGS {
        uuid id PK
        uuid certificate_id FK
        uuid verifier_id FK
        string uploaded_file_hash
        string verification_result
        string verifier_email
        timestamp checked_at
    }

    CERTIFICATE_SHARES {
        uuid id PK
        uuid certificate_id FK
        uuid student_id FK
        string share_token UK
        string share_url
        timestamp created_at
        timestamp expires_at
        boolean is_active
    }

    REVOCATION_LOGS {
        uuid id PK
        uuid certificate_id FK
        uuid revoked_by_admin_id FK
        string revocation_reason
        string blockchain_tx_hash
        timestamp revoked_at
    }

    USERS ||--o{ CERTIFICATES : "student owns"
    USERS ||--o{ CERTIFICATES : "admin issues"
    USERS ||--o{ VERIFICATION_LOGS : "verifier checks"
    USERS ||--o{ CERTIFICATE_SHARES : "student shares"

    INSTITUTIONS ||--o{ CERTIFICATES : "issues"
    INSTITUTIONS ||--o{ ADMIN_APPOINTMENTS : "has appointed admins"

    ADMIN_APPOINTMENTS }o--|| USERS : "appoints user as admin"
    ADMIN_APPOINTMENTS }o--|| INSTITUTIONS : "belongs to institution"

    CERTIFICATES ||--|| BLOCKCHAIN_RECORDS : "has blockchain proof"
    CERTIFICATES ||--o{ VERIFICATION_LOGS : "verified through"
    CERTIFICATES ||--o{ CERTIFICATE_SHARES : "shared by link"
    CERTIFICATES ||--o{ REVOCATION_LOGS : "may be revoked"

    USERS ||--o{ REVOCATION_LOGS : "admin revokes"