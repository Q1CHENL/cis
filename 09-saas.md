# Software as a Service

- service more valuable than software alone: administration, security, high availability, core software can be open source
- startup and non-conservative customers expect SaaS
- cost optimization is a primary goal
- benchmarking is necessary to find out which services to use
- distributed systems are hard: scalability and elasticity are not always achieved in practice

## DevOps

- software developers: development + operations, release every 1-2 weeks (frequent), 2 versions: current and next
- dev feel the pain of ops: more robust software, better design

## Designing pricing models

- important, hard to change even if new model is better for most
  - usage pricing
  - flat rate: 10$/month
  - tiers: free, standard, premium (market segmentation)
  - provisioned performance vs. metered consumption
  - opaque (price discrimination)
- considerations (trade-offs)
  - simplicity
  - predictability
  - psychology
  - competition
  - alignment of incentives between customers and service provider
  - internal costs

### Multi cloud support

- possible but not trivial
- snowflakes can achieve this: operates open source OLTP DBMS etc

## Security in the cloud

- multi-tenancy can make security issues disastrous
- per-tenant VMs > containers on a shared VM > shared VMs (safer)
- encrypted backups

### General Data Protection Regulation (GDPR)

- personal data
- data subject
- data processing
- data controller
- data processor
