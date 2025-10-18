<h1>Business Model<h1>

```mermaid
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
```
```mermaid
graph TD
    %% Define Nodes with Icons and Styling
    A[<i class='fa fa-user'></i> Rural Youth/Worker]:::user --> B{Access Platform};
    B --> C{Vernacular/Voice Input};
    C --> D(AI Non-Formal Skill Indexing);
    D --> E{AI-Enabled Recommendation Engine};
    
    E --> F[<i class='fa fa-map-marker'></i> Hyper-Local Job Index];
    F --> G(Job Match & Skill Gap Analysis);
    
    G --> H{Match Found?};
    
    H -- Yes: Direct Match --> I[<i class='fa fa-check-circle'></i> Job/Livelihood Opportunity];
    H -- No: Skill Gap Exists --> J(Personalized Skill-Gap Analysis);
    
    J --> K[<i class='fa fa-graduation-cap'></i> Local Training Recommendation];
    
    K --> L(Career Pathing: Upskill);
    L --> E; %% Loop back to the recommendation engine after upskilling

    I --> M[<i class='fa fa-rocket'></i> Sustainable Employment/Self-Sufficiency];
    
    %% Define Node Styles
    classDef user fill:#9ED6E7,stroke:#0077B6,stroke-width:2px;
    classDef ai fill:#D4EDDA,stroke:#155724,stroke-width:2px;
    classDef gap fill:#FFF3CD,stroke:#856404,stroke-width:2px;
    classDef result fill:#DCF8C6,stroke:#38761D,stroke-width:2px;
    
    class A,M user;
    class D,E ai;
    class J gap;
    class I,K,L,F result;
```