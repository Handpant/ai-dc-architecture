```mermaid
graph TD

Investor[USD Institutional Investor / Infra Fund]
VCC[Singapore VCC]

Investor --> VCC

subgraph SPV_1 [SPV 1 - Data Centre (Infra SPV)]
    direction TB
    DC["Data Centre Platform
Initial 2 MW June
Scale 10-12 MW"]
    Land["Land"]
    Building["Building / Modular DC"]
    Infra["Power and Cooling"]
end

VCC --> SPV_1

subgraph SPV_2 [SPV 2 - Project Equipment (Compute SPV)]
    direction TB
    GPUs["GPUs
June 1500-2000
Target 8000"]
    Servers["AI Servers"]
end

VCC --> SPV_2

Tenant[Tenant]
Tenant -->|USD per GPU| SPV_2

SPV_2 -->|DC Lease and Services| SPV_1

Cybersault["Cybersault Operator"]
SPV_1 -->|Facilities SLA| Cybersault
SPV_2 -->|Platform Ops SLA| Cybersault

June["June Go Live
2 MW Pilot"]
June -.-> SPV_1
June -.-> SPV_2

ExitInfra["Exit Infra Fund"]
ExitCompute["Exit Hyperscaler"]

SPV_1 --- ExitInfra
SPV_2 --- ExitCompute
```
