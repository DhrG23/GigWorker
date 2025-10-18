graph LR
    %% 🌟 Main Flow: Value to Users and Data to Payers
    
    %% === User & Input Side ===
    subgraph A[User Value & Data Input]
        R_Y[Rural Youth 👩‍🌾]
        LE[Local Employers / SMEs 🏭]
        SP[Skill Training Providers 🎓]
    end

    %% === Core Platform Logic ===
    subgraph B[Core Platform Logic 💡]
        PM[Platform Match Engine ⚙️]
    end

    %% === Revenue Flow ===
    subgraph C[Revenue Flow 💰]
        R2_LE[Employer Subscriptions & Premium Listings]
        R3_SP[Training Provider Lead Gen Fees CPA]
        R4_GOV[Govt / NGO Data Licensing Fees]
        R1_PREMIUM[Premium Services 💎]
    end

    %% === Clean, Straight Connections ===
    R_Y -->|Input: Informal Skills & Needs| PM
    LE -->|Input: Hyper-Local Jobs| PM
    SP -->|Input: Course Offerings| PM

    PM -->|Matched Jobs & Training Gaps| R_Y
    PM -->|Qualified Candidates & Skill Demand| LE
    PM -->|Targeted Leads| SP

    LE -->|Billed for High-Quality Matches| R2_LE
    SP -->|Billed for High-Intent Enrollments| R3_SP
    R_Y -.->|Provides Aggregate Data| GOV[Govt / NGOs]
    GOV -->|Pays for Policy Insights| R4_GOV
    R_Y -->|Optional Service Fee| R1_PREMIUM

    %% === Styles ===
    linkStyle default stroke-width:2px,fill:none,stroke:#555
    classDef node fill:#fff,stroke:#333,stroke-width:1.5px,color:#000
    classDef highlight fill:#f9f,stroke:#000,stroke-width:2px
    classDef revenue fill:#ccf,stroke:#000,stroke-width:2px
    classDef user fill:#aaf,stroke:#000,stroke-width:2px

    class PM highlight
    class R2_LE,R3_SP,R4_GOV,R1_PREMIUM revenue
    class R_Y user
