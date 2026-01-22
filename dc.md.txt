# AI Data Center SPV Architecture

```mermaid
graph TD
    Investor[USD Institutional Investor / Infra Fund] -->|Equity / Debt| VCC[Singapore VCC / Master Holdco]

    subgraph SPV_1 [SPV 1: Infra & Real Estate]
        direction TB
        Land[Freehold Land Titles<br/>(Mumbai / Chennai)]
        Shell[Powered Shell & Building]
        Utility[Primary Power Substation<br/>+ Liquid Cooling Loops]
    end
    VCC -->|Equity| SPV_1

    subgraph SPV_2 [SPV 2: AI Technology Stack]
        direction TB
        GPUs[8,000 NVIDIA B300 GPUs]
        Servers[High-Density Rack Architecture]
        Networking[InfiniBand / Quantum-X800 Fabric]
    end
    VCC -->|Equity / Lease Finance| SPV_2

    Tenant[Global AI Lab / Enterprise Tenant] -->|USD Payments| SPV_2
    SPV_2 -->|Monthly Infrastructure Fee| SPV_1

    Operator[Infinie Cybersault] -.->|SLA-Based Management| SPV_1
    Operator -.->|Technical Ops & Optimization| SPV_2

    SPV_1 --- Exit1[Exit: Global Infra Fund / REIT]
    SPV_2 --- Exit2[Exit: Strategic Hyperscaler / IPO]
