# NOMU System Blueprint (Prototype)

- Clients (Web/Mobile) per role.
- API Gateway -> Auth, Child Journey, Health, Education, Referral, Wallet/CSR, KPIs.
- PostgreSQL + Redis + Object Storage.
- Integrations: NPHIES, Noor, National SSO.

```mermaid
flowchart TD
  U[Users] -->|JWT| GW[API Gateway]
  GW --> AUTH[Auth]
  GW --> R[Referral]
  GW --> W[Wallet/CSR]
  GW --> K[KPI]

  subgraph Data
    DB[(PostgreSQL)]
    CA[(Redis)]
    ST[(Object Storage)]
  end
  AUTH --> DB
  R --> DB
  W --> DB
  K --> DB
```
