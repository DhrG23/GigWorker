graph TD
    %% Main Flow: Value to Users and Data to Payers
    
    subgraph A[User Value & Data Input]
        R_Y[Rural Youth] -->|Input: Informal Skills & Needs| PM(Platform Match Engine)
        LE[Local Employers / SMEs] -->|Input: Hyper-Local Jobs| PM
        SP[Skill Training Providers] -->|Input: Course Offerings| PM
    end
    
    subgraph B[Core Platform Logic]
        PM -->|Output 1: Matched Jobs & Training Gaps| R_Y
        PM -->|Output 2: Qualified Candidates & Skill Demand| LE
        PM -->|Output 3: Targeted Leads| SP
    end
    
    %% Revenue Generation (Right Side)
    subgraph C[Revenue Flow]
        R2_LE[Employer Subscriptions & Premium Listing Fees]
        R3_SP[VTC/Provider Lead Generation Fees (CPA)]
        R4_GOV[Govt/NGO Data Licensing Fees]
    end

    %% Connections
    LE -- Billed For High-Quality Matches --> R2_LE
    SP -- Billed For High-Intent Enrollments --> R3_SP
    
    R_Y -. Provides Aggregate Data .-> GOV[Govt / NGOs]
    GOV -- Pays for Policy Insights --> R4_GOV
    
    %% Optional/Secondary Revenue (Dashed line)
    R_Y -- Optional Service Fee --> R1_PREMIUM[Premium Services]
    
    %% Style Definitions (Making key elements stand out)
    style PM fill:#f9f,stroke:#333,stroke-width:2px,color:#000
    style R2_LE fill:#ccf,stroke:#000,stroke-width:2px,color:#000
    style R3_SP fill:#ccf,stroke:#000,stroke-width:2px,color:#000
    style R4_GOV fill:#ccf,stroke:#000,stroke-width:2px,color:#000
    style R1_PREMIUM fill:#ccf,stroke:#000,stroke-width:2px,color:#000
    style R_Y fill:#aaf,stroke:#000,stroke-width:2px,color:#000
