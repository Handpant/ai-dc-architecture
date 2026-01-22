```mermaid
graph TD

%% =========================
%% CAPITAL & HOLDCO
%% =========================
Investor[USD Institutional Investor / Infra Fund]
VCC[Singapore VCC]

Investor -->|Equity / Debt| VCC

%% =========================
%% SPV 1 – DATA CENTRE (INFRA)
%% =========================
subgraph SPV_1 [SPV 1 – Data Centre (Infra SPV)]
    direction TB
    DC["Data Centre Platform
Initial: 2 MW (June Pilot)
Scale: 10–12 MW"]
    Land["Land
(Owned / Optioned)"]
    Building["Building / Modular DC"]
    Infra["Power, Cooling & Utilities"]
end

VCC -->|Equity| SPV_1

DC --> Land
DC --> Building
DC --> Infra

%% =========================
%% SPV 2 – PROJECT EQUIPMENT
%% =========================
subgraph SPV_2 [SPV 2 – Project Equipment (Compute SPV)]
    direction TB
    GPUs["GPUs
June: 1,500–2,000
Target: ~8,000"]
    Servers["AI Servers / Racks"]
end

VCC -->|Equity / Lease Finance| SPV_2

%% =========================
%% TENANT ECONOMICS
%% =========================
Tenant[Tenant / AI Workload Owner]

Tenant -->|USD / GPU (All-in)| SPV_2

%% =========================
%% INTER-SPV ECONOMICS (KEY)
%% =========================
SPV_2 -->|DC Lease + Power + Cooling Fees| SPV_1

%% =========================
%% OPERATOR – CYBERSAULT
%% =========================
Cybersault["Cybersault
(Specialist DC & AI Ops Operator)"]

SPV_1 -->|DC Operations & Facilities (SLA)| Cybersault
SPV_2 -->|Platform Ops, Monitoring & Optimisation| Cybersault

%% =========================
%% JUNE GO-LIVE OVERLAY
%% =========================
June["June Go-Live Pilot
• 2 MW live capacity
• Hybrid liquid cooling
• 1,500–2,000 GPUs
• Revenue-generating"]

June -.-> SPV_1
June -.-> SPV_2

%% =========================
%% EXIT PATHS
%% =========================
ExitInfra["Exit:
Global Infra Fund / REIT"]
ExitCompute["Exit:
Hyperscaler / Strategic Buyer"]

SPV_1 --- ExitInfra
SPV_2 --- ExitCompute

%% =========================
%% IRR ANNOTATIONS (SAFE)
%% =========================
IRR1["IRR: 14–18%
Yield-oriented
Land + DC Re-rating"]
IRR2["IRR: 22–28%
Compute upside
USD GPU contracts"]

IRR1 -.-> SPV_1
IRR2 -.-> SPV_2

%% =========================
%% STYLING – INVESTOR BLUE / GREY
%% =========================
classDef capital fill:#0B3C5D,color:#ffffff,stroke:#0B3C5D,stroke-width:2px
classDef infra fill:#E5E7EB,color:#111827,stroke:#6B7280,stroke-width:1.5px
classDef compute fill:#2563EB,color:#ffffff,stroke:#1E40AF,stroke-width:1.5px
classDef neutral fill:#F3F4F6,color:#111827,stroke:#9CA3AF,stroke-width:1px
classDef annotation fill:#DBEAFE,color:#1E3A8A,stroke:#93C5FD,stroke-width:1px
classDef exit fill:#CBD5E1,color:#0F172A,stroke:#64748B,stroke-width:1.5px

class Investor,VCC capital
class SPV_1,DC,Land,Building,Infra infra
class SPV_2,GPUs,Servers compute
class Tenant,Cybersault neutral
class June,IRR1,IRR2 annotation
class ExitInfra,ExitCompute exit
```
