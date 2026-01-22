```mermaid
graph TD

%% CAPITAL & HOLDCO
Investor[USD Institutional Investor / Infra Fund]
VCC[Singapore VCC]

Investor -->|Equity / Debt| VCC

%% SPV 1 - DATA CENTRE (INFRA)
subgraph SPV_1 [SPV 1 - Data Centre (Infra SPV)]
    direction TB
    DC["Data Centre Platform
Initial: 2 MW (June Pilot)
Scale: 10-12 MW"]
    Land["Land (Owned / Optioned)"]
    Building["Building / Modular DC"]
    Infra["Power, Cooling & Utilities"]
end

VCC -->|Equity| SPV_1

DC --> Land
DC --> Building
DC --> Infra

%% SPV 2 - PROJECT EQUIPMENT
subgraph SPV_2 [SPV 2 - Project Equipment (Compute SPV)]
    direction TB
    GPUs["GPUs
June: 1,500-2,000
Target: ~8,000"]
    Servers["AI Servers / Racks"]
end

VCC -->|Equity / Lease Finance| SPV_2

%% TENANT ECONOMICS
Tenant[Tenant / AI Workload Owner]
Tenant -->|USD / GPU (All-in)| SPV_2

%% INTER-SPV ECONOMICS
