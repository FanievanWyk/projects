# Backup & Recovery — Illustrative Reference Model

> This model uses fictional service names and deliberately omits production settings.

```mermaid
flowchart LR
    Workloads[Production Workloads] --> Local[Local Recovery Layer]
    Workloads --> Cloud[Cloud-Native Protection]
    Local --> Repository[Protected Backup Repository]
    Repository --> Offsite[Offsite Replication]
    Offsite --> Recovery[Alternate Recovery Location]
    Local --> Tests[Restore Validation]
    Offsite --> Tests
    Tests --> Evidence[Recovery Evidence and Improvements]
```

## Recovery design questions

1. Which services are most important to operations?
2. What data loss is tolerable for each service?
3. How long can each service remain unavailable?
4. Which dependencies must recover first?
5. What happens if the primary site or identity platform is unavailable?
6. How is successful restoration demonstrated?
7. Who owns the decision to invoke recovery?

## Good-practice themes

- Multiple protection layers
- Separation of production and backup risk
- Offsite resilience
- Tested restoration
- Dependency-aware recovery order
- Clear ownership and documentation
- Continual improvement after each test or incident
