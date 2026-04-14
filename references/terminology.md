# HR & ATS Terminology Reference

Load this file when diagnosing or rewriting resume bullet points. It contains two sections:
1. **Power Verbs** — strong action verbs HR and recruiters respond to, organized by category
2. **Keyword Translation Table** — maps overly technical jargon to HR-friendly equivalents

---

## Power Verbs by Category

Use these to vary sentence openings and signal leadership, impact, and ownership.

### Leadership & Strategy
Spearheaded, Championed, Drove, Directed, Orchestrated, Pioneered, Established, Defined, Shaped, Steered

### Building & Engineering
Architected, Engineered, Designed, Built, Developed, Implemented, Launched, Deployed, Scaled, Automated

### Improvement & Optimization
Streamlined, Accelerated, Optimized, Reduced, Eliminated, Revamped, Modernized, Transformed, Enhanced, Consolidated

### Collaboration & Communication
Partnered with, Aligned, Coordinated, Advised, Enabled, Mentored, Facilitated, Bridged (gap between X and Y)

### Analysis & Problem-Solving
Diagnosed, Identified, Uncovered, Resolved, Investigated, Evaluated, Assessed, Benchmarked

### Delivery & Results
Delivered, Achieved, Generated, Produced, Completed, Exceeded, Secured, Captured

**Usage rule:** No two consecutive bullets in the same job section should start with the same verb. If the user's original bullets all start with "Built" or "Developed", flag it and rotate through these categories.

---

## Keyword Translation Table

Maps overly technical terms to HR/ATS-friendly equivalents. Left column is what engineers write; right column is what to use instead.

### Storage & Data Formats
| Engineer Says | HR-Friendly Version |
|---|---|
| Parquet / ORC / Avro | columnar storage formats |
| Delta Lake / Iceberg / Hudi | open table formats (or omit) |
| star schema / snowflake schema | dimensional data models |
| fact table / dimension table | data models |
| materialized views | pre-computed data views (or omit) |
| partitioning / bucketing | data optimization techniques |

### Data Processing
| Engineer Says | HR-Friendly Version |
|---|---|
| idempotent upserts | data integrity controls |
| deterministic deduplication | deduplication logic |
| schema-drift guards | schema validation |
| MinHash / LSH / Jaccard | near-duplicate detection |
| backpressure handling | throughput optimization |
| windowed aggregation | time-based aggregation |
| late-arriving data handling | data completeness logic |
| CDC (Change Data Capture) | real-time data synchronization |

### Infrastructure & DevOps
| Engineer Says | HR-Friendly Version |
|---|---|
| observability | monitoring and alerting |
| decoupled ingestion | modular data ingestion |
| container orchestration | Docker/Kubernetes |
| infrastructure as code | Terraform/CloudFormation |
| blue-green deployment | zero-downtime deployment |
| RBAC | role-based access control |

### BI & Reporting
| Engineer Says | HR-Friendly Version |
|---|---|
| T-SQL / DAX / Power Query (M) | SQL / Power BI |
| SSIS | ETL pipelines |
| SSAS cubes | analytical models |
| row-level security | data access governance |
| semantic layer | business metrics layer |

### SAP-Specific (for SAP roles only — keep if targeting SAP jobs)
| Engineer Says | HR-Friendly Version (non-SAP jobs) |
|---|---|
| RFC-based integrations | API/system integrations |
| BAPI calls | system interface calls |
| ALV reports | interactive reports |
| ABAP OOP | custom development |
| SAP ECC modules | ERP system |
| Work Order Inquiry / Technical Review | (omit internal system names — describe the function instead) |

### Cloud & Platform
| Engineer Says | HR-Friendly Version |
|---|---|
| S3 lifecycle policies | cloud storage optimization |
| VPC peering | network architecture |
| IAM policies | access management |
| EMR / Glue / Lambda | AWS data services |

---

## ATS (Applicant Tracking System) Keywords

These are the terms that ATS systems and recruiters actively search for. Make sure every resume includes relevant ones from the target job description.

### Must-Have for Data Engineering Roles
Python, SQL, AWS/GCP/Azure, ETL, data pipeline, data warehouse, Spark/PySpark, Airflow, Kafka, Snowflake, Databricks, dbt, Docker, Terraform, Git, CI/CD, data quality, data governance

### Must-Have for Analytics / BI Roles
SQL, Python, Tableau, Power BI, dashboard, KPI, reporting, data analysis, A/B testing, stakeholder, cross-functional

### Must-Have for DevOps / Platform Roles
CI/CD, Docker, Kubernetes, Terraform, AWS/GCP/Azure, monitoring, automation, microservices, Git, infrastructure

**Usage rule:** When rewriting, cross-check the user's bullet points against these keyword lists. If a highly relevant keyword is missing from their resume but implied by their work, suggest adding it explicitly.
