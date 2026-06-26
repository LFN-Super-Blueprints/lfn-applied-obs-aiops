# D2 — Observability Landscape Assessment: Operator Template

**Operator:** _[Organization Name]_
**Completed by:** _[Name(s) and Role(s)]_
**Date:** _[YYYY-MM-DD]_
**Return deadline:** _[TBD - set in kickoff meeting]_

> Complete one copy per operator organization. Sections are organized by domain, so route each domain section to the appropriate team if needed. Use the provided field options where listed; add free-text only where indicated. Partial returns are fine. Submit what you have by the deadline and flag incomplete sections.

---

## 1. Organization overview

| Field | Response |
|---|---|
| Organization name | |
| Primary operating regions | |
| Subscriber base (order of magnitude) | |
| Network generations in production (4G / 5G NSA / 5G SA / Fixed) | |
| Cloud strategy (on-prem / hybrid / public cloud / multi-cloud) | |
| Primary cloud provider(s) if applicable | |
| Kubernetes distribution(s) in use | |
| TM Forum AN self-assessed level (overall) | L0 / L1 / L2 / L3 / L4 / L5 |
| TM Forum AN target level and target year | |

---

## 2. Per-domain assessment

Complete the following subsections for each domain that is relevant to your organization. Skip domains that are not applicable.

---

### 2.1 Radio Access Network (RAN)

#### 2.1.1 Vendor and tech stack

| Field | Response |
|---|---|
| Primary RAN vendor(s) | |
| O-RAN compliant? | Yes / Partial / No |
| RIC deployed? (Near-RT / Non-RT / Both / None) | |
| xApps / rApps in production (list) | |
| CU/DU split architecture? | Yes / No |
| Fronthaul / midhaul protocol | eCPRI / CPRI / Other: ___ |
| AI-RAN capabilities deployed | None / Energy saving / Beam mgmt / Other: ___ |
| Deployment model | On-prem / Hybrid / Cloud-RAN |

#### 2.1.2 Telemetry and data

| Signal type | Exists? | Protocol / format | Collection method | Volume (events/sec or GB/day) | Destination system | Retention |
|---|---|---|---|---|---|---|
| Performance metrics (KPIs) | Yes / No | | Push / Pull / Stream | | | |
| Alarms / faults | Yes / No | | | | | |
| Configuration data | Yes / No | | | | | |
| Call traces / CDRs | Yes / No | | | | | |
| RIC telemetry | Yes / No | | | | | |
| Fronthaul / midhaul metrics | Yes / No | | | | | |

**Protocols in use** (check all that apply): [ ] OpenTelemetry [ ] gNMI [ ] SNMP [ ] VES [ ] 3GPP XML PM [ ] Proprietary: ___

**eBPF in use for RAN observability?** Yes / No / Evaluating

#### 2.1.3 Cross-domain correlation

| Question | Response |
|---|---|
| Can you correlate RAN alarms to transport events today? | Yes / Partial / No |
| Can you correlate RAN performance to customer experience? | Yes / Partial / No |
| What identifier links RAN data to other domains? | |
| Where does correlation break down? | _[free text]_ |

#### 2.1.4 Data sharing comfort level

| Data type | Sharing level |
|---|---|
| Statistical profile (distributions, rates, cardinality) | Can share / Needs anonymization / Schema only / Cannot share |
| Synthetic sample (fake but realistic records) | Can share / Needs review / Cannot share |
| Schema / data dictionary | Can share / Cannot share |

---

### 2.2 Transport

#### 2.2.1 Vendor and tech stack

| Field | Response |
|---|---|
| Primary transport vendor(s) | |
| Technologies in production | IP/MPLS / Segment Routing / Optical DWDM / Microwave / Other: ___ |
| SDN controller deployed? | Yes (which: ___) / No |
| Time-sensitive networking (TSN) in use? | Yes / No / Planned |

#### 2.2.2 Telemetry and data

| Signal type | Exists? | Protocol / format | Collection method | Volume | Destination system | Retention |
|---|---|---|---|---|---|---|
| Interface metrics (utilization, errors) | Yes / No | | | | | |
| Routing / topology events | Yes / No | | | | | |
| Optical layer telemetry | Yes / No | | | | | |
| Latency / jitter measurements | Yes / No | | | | | |
| SDN controller telemetry | Yes / No | | | | | |

**Protocols in use**: [ ] gNMI [ ] SNMP [ ] Streaming telemetry [ ] NETCONF/YANG [ ] sFlow/NetFlow [ ] OpenTelemetry [ ] Proprietary: ___

#### 2.2.3 Cross-domain correlation

| Question | Response |
|---|---|
| Can you correlate transport faults to RAN / core impact? | Yes / Partial / No |
| End-to-end latency measurement across transport? | Yes / Partial / No |
| What's the hardest thing to correlate across transport? | _[free text]_ |

#### 2.2.4 Data sharing comfort level

| Data type | Sharing level |
|---|---|
| Statistical profile | Can share / Needs anonymization / Schema only / Cannot share |
| Synthetic sample | Can share / Needs review / Cannot share |
| Schema / data dictionary | Can share / Cannot share |

---

### 2.3 5G / 6G Core

#### 2.3.1 Vendor and tech stack

| Field | Response |
|---|---|
| Core vendor(s) | |
| Architecture | 5G SA SBA / 5G NSA / 4G EPC / Converged |
| Cloud-native NFs? | Yes (containerized) / VNF / Mixed |
| Service mesh in use? | Yes (which: ___) / No |
| Network slicing in production? | Yes / Trial / No |

#### 2.3.2 Telemetry and data

| Signal type | Exists? | Protocol / format | Collection method | Volume | Destination system | Retention |
|---|---|---|---|---|---|---|
| Control-plane signaling metrics | Yes / No | | | | | |
| User-plane throughput / latency | Yes / No | | | | | |
| SBA inter-NF tracing | Yes / No | | | | | |
| NF lifecycle events (scale, restart, fail) | Yes / No | | | | | |
| Slice-level metrics | Yes / No | | | | | |
| Session / subscriber analytics | Yes / No | | | | | |

**Distributed tracing for SBA in use?** Yes (which: ___) / No / Planned

#### 2.3.3 Cross-domain correlation

| Question | Response |
|---|---|
| Can you trace a subscriber session end-to-end (UE → RAN → Core)? | Yes / Partial / No |
| Can you correlate NF faults to infrastructure (K8s/VM) events? | Yes / Partial / No |
| What visibility are you missing in the core? | _[free text]_ |

#### 2.3.4 Data sharing comfort level

| Data type | Sharing level |
|---|---|
| Statistical profile | Can share / Needs anonymization / Schema only / Cannot share |
| Synthetic sample | Can share / Needs review / Cannot share |
| Schema / data dictionary | Can share / Cannot share |

---

### 2.4 OSS

#### 2.4.1 Vendor and tech stack

| Field | Response |
|---|---|
| Primary OSS platform(s) | |
| Service orchestration tool | |
| Inventory / CMDB system | |
| Service assurance platform | |
| Observability platform (if separate from assurance) | |
| AIOps platform (if any) | None / Vendor: ___ / In-house |
| ONAP deployed? | Yes / Partial / No / Evaluating |

#### 2.4.2 Telemetry and data

| Signal type | Exists? | Protocol / format | Volume | Destination system | Retention |
|---|---|---|---|---|---|
| Service health metrics | Yes / No | | | | |
| Topology / inventory events | Yes / No | | | | |
| Orchestration workflow logs | Yes / No | | | | |
| Alarm correlation output | Yes / No | | | | |
| Ticketing / incident data | Yes / No | | | | |

#### 2.4.3 Cross-domain correlation

| Question | Response |
|---|---|
| Single pane of glass across RAN + Transport + Core? | Yes / Partial / No |
| Can you tie SLA breaches back to specific infrastructure faults? | Yes / Partial / No |
| MTTR for top 3 incident categories | _[free text]_ |
| MTTD for top 3 incident categories | _[free text]_ |

#### 2.4.4 Data sharing comfort level

| Data type | Sharing level |
|---|---|
| Statistical profile | Can share / Needs anonymization / Schema only / Cannot share |
| Synthetic sample | Can share / Needs review / Cannot share |
| Schema / data dictionary | Can share / Cannot share |

---

### 2.5 BSS

#### 2.5.1 Vendor and tech stack

| Field | Response |
|---|---|
| CRM platform | |
| Billing / charging system | |
| Order management system | |
| Product catalog | |
| Customer experience management tool | |

#### 2.5.2 Telemetry and data

| Signal type | Exists? | Format | Volume | Destination system | Retention |
|---|---|---|---|---|---|
| Customer interaction events | Yes / No | | | | |
| NPS / CSAT scores | Yes / No | | | | |
| Churn indicators | Yes / No | | | | |
| Billing anomalies / disputes | Yes / No | | | | |
| Revenue leakage signals | Yes / No | | | | |
| Usage / CDR data | Yes / No | | | | |

#### 2.5.3 Cross-domain correlation

| Question | Response |
|---|---|
| Can you tie customer complaints to network faults? | Yes / Partial / No |
| Can you correlate billing anomalies to service delivery events? | Yes / Partial / No |
| Do you have labeled churn data with network quality features? | Yes / Partial / No |

#### 2.5.4 Data sharing comfort level

| Data type | Sharing level |
|---|---|
| Statistical profile | Can share / Needs anonymization / Schema only / Cannot share |
| Synthetic sample | Can share / Needs review / Cannot share |
| Schema / data dictionary | Can share / Cannot share |

---

### 2.6 Edge & MEC

#### 2.6.1 Vendor and tech stack

| Field | Response |
|---|---|
| Edge platform(s) | |
| Kubernetes distribution at edge | |
| Edge UPF deployed? | Yes / No / Planned |
| Hyperscaler edge in use? | AWS Wavelength / Azure Edge Zones / GCP Distributed Cloud / None |
| Number of edge sites (order of magnitude) | |

#### 2.6.2 Telemetry and data

| Signal type | Exists? | Protocol / format | Volume | Destination system | Retention |
|---|---|---|---|---|---|
| Edge compute metrics (CPU, memory, GPU) | Yes / No | | | | |
| Edge application metrics | Yes / No | | | | |
| Edge-to-core latency measurements | Yes / No | | | | |
| Edge UPF telemetry | Yes / No | | | | |

#### 2.6.3 Cross-domain correlation

| Question | Response |
|---|---|
| Can you correlate edge app performance to RAN / transport quality? | Yes / Partial / No |
| Centralized observability for all edge sites? | Yes / Partial / No |

#### 2.6.4 Data sharing comfort level

| Data type | Sharing level |
|---|---|
| Statistical profile | Can share / Needs anonymization / Schema only / Cannot share |
| Synthetic sample | Can share / Needs review / Cannot share |
| Schema / data dictionary | Can share / Cannot share |

---

### 2.7 Non-Terrestrial Networks (NTN)

> Skip if not applicable.

#### 2.7.1 Vendor and tech stack

| Field | Response |
|---|---|
| NTN type | LEO Satellite / GEO Satellite / HAPS / None / Planned |
| 3GPP NTN release | Rel-17 / Rel-18 / Pre-standard / N/A |
| Integration model | Direct-to-device / Backhaul / Both |

#### 2.7.2 Telemetry and data

| Signal type | Exists? | Protocol / format | Volume | Destination system | Retention |
|---|---|---|---|---|---|
| Satellite link metrics | Yes / No | | | | |
| Latency-aware telemetry | Yes / No | | | | |
| Handover events (terrestrial ↔ NTN) | Yes / No | | | | |

#### 2.7.3 Data sharing comfort level

| Data type | Sharing level |
|---|---|
| Statistical profile | Can share / Needs anonymization / Schema only / Cannot share |
| Schema / data dictionary | Can share / Cannot share |

---

### 2.8 Cloud Infrastructure

#### 2.8.1 Vendor and tech stack

| Field | Response |
|---|---|
| Infrastructure model | Bare metal / VMs / Kubernetes / Mixed |
| Kubernetes distribution(s) | OpenShift / Rancher / Upstream / Wind River / Other: ___ |
| Multi-cluster management | Yes (which: ___) / No |
| GPU / AI accelerator infrastructure | NVIDIA (which: ___) / AMD / Intel / None |
| Hybrid / sovereign cloud requirements | Yes (describe: ___) / No |

#### 2.8.2 Telemetry and data

| Signal type | Exists? | Protocol / format | Volume | Destination system | Retention |
|---|---|---|---|---|---|
| Infrastructure metrics (compute, storage, network) | Yes / No | | | | |
| Kubernetes metrics and events | Yes / No | | | | |
| Container / pod logs | Yes / No | | | | |
| Distributed traces (application level) | Yes / No | | | | |
| GPU utilization metrics | Yes / No | | | | |
| Cluster-level events (scaling, failures) | Yes / No | | | | |

**Observability stack**: [ ] Prometheus [ ] Grafana [ ] Elasticsearch [ ] Jaeger [ ] OpenTelemetry Collector [ ] Splunk [ ] Datadog [ ] Dynatrace [ ] Proprietary: ___

#### 2.8.3 Cross-domain correlation

| Question | Response |
|---|---|
| Can you correlate K8s pod issues to NF / application impact? | Yes / Partial / No |
| Multi-cluster observability in place? | Yes / Partial / No |
| Unified view of VM + container workloads? | Yes / Partial / No |

#### 2.8.4 Data sharing comfort level

| Data type | Sharing level |
|---|---|
| Statistical profile | Can share / Needs anonymization / Schema only / Cannot share |
| Synthetic sample | Can share / Needs review / Cannot share |
| Schema / data dictionary | Can share / Cannot share |

---

## 3. AIOps maturity

### 3.1 Current AI/ML in production

| Use case | In production? | Technique | Domain | Model type | Accuracy / effectiveness | Notes |
|---|---|---|---|---|---|---|
| Anomaly detection | Yes / PoC / No | | | Classic ML / GenAI / Hybrid | | |
| Fault prediction | Yes / PoC / No | | | Classic ML / GenAI / Hybrid | | |
| Root cause analysis | Yes / PoC / No | | | Classic ML / GenAI / Hybrid | | |
| Capacity planning | Yes / PoC / No | | | Classic ML / GenAI / Hybrid | | |
| Energy optimization | Yes / PoC / No | | | Classic ML / GenAI / Hybrid | | |
| Customer experience | Yes / PoC / No | | | Classic ML / GenAI / Hybrid | | |
| Revenue assurance | Yes / PoC / No | | | Classic ML / GenAI / Hybrid | | |
| Security / threat detection | Yes / PoC / No | | | Classic ML / GenAI / Hybrid | | |
| Other: ___ | Yes / PoC / No | | | Classic ML / GenAI / Hybrid | | |

### 3.2 Data engineering maturity

| Question | Response |
|---|---|
| Do you have a centralized data lake / lakehouse? | Yes / In progress / No |
| Feature store in use? | Yes (which: ___) / No |
| Data labeling process for supervised learning? | Systematic / Ad-hoc / None |
| Data quality monitoring in place? | Yes / Partial / No |
| Top 3 data quality issues | _[free text]_ |

### 3.3 ML platform

| Question | Response |
|---|---|
| ML platform in use | Kubeflow / MLflow / SageMaker / Vertex / In-house / None / Other: ___ |
| Model serving infrastructure | KServe / vLLM / TF Serving / Triton / None / Other: ___ |
| Model monitoring / drift detection | Yes (which: ___) / No |
| LLM / SLM usage for operations | Yes (which models, what tasks: ___) / Evaluating / No |

---

## 4. Pain points and priorities

### 4.1 Top operational pain points

Rank your top 5 operational pain points (1 = most painful):

| Rank | Pain point | Domain(s) affected | Estimated impact (hours/month or cost) |
|---|---|---|---|
| 1 | | | |
| 2 | | | |
| 3 | | | |
| 4 | | | |
| 5 | | | |

### 4.2 What Breaks at 3 AM?

_Describe the top 3 recurring incidents that trigger after-hours response. Include: what triggers the alarm, who responds, how it's diagnosed, how long it takes to resolve, and what would need to be true to automate the response._

1.
2.
3.

### 4.3 What's been tried and didn't work?

_Any observability or AIOps initiatives that were tried and didn't work out? What went wrong?_

| Initiative | What happened | Why it failed |
|---|---|---|
| | | |
| | | |

---

## 5. TM Forum Autonomous Networks roadmap

### 5.1 Per-domain AN level assessment

| Domain | Current level (L0-L5) | Target level | Target year | What's blocking the next level? |
|---|---|---|---|---|
| RAN | | | | |
| Transport | | | | |
| 5G Core | | | | |
| OSS | | | | |
| BSS | | | | |
| Edge / MEC | | | | |
| NTN | | | | |
| Cloud Infra | | | | |
| **End-to-End** | | | | |

### 5.2 What's blocking autonomy?

_For the domain with the largest gap between current and target AN level, describe the top 3 blockers:_

1.
2.
3.

---

## 6. Use case prioritization

From the WG's five anchor use cases, rank by relevance to your organization (1 = highest priority):

| Rank | Use case | Relevance | Data available today? | Willing to co-develop? |
|---|---|---|---|---|
| | 5G Fault Prediction | High / Medium / Low | Yes / Partial / No | Yes / No |
| | Customer Churn Reduction | High / Medium / Low | Yes / Partial / No | Yes / No |
| | Revenue Assurance (RAFM) | High / Medium / Low | Yes / Partial / No | Yes / No |
| | Energy Optimization | High / Medium / Low | Yes / Partial / No | Yes / No |
| | Service Assurance Latency Prediction | High / Medium / Low | Yes / Partial / No | Yes / No |

**Other use cases you'd like the WG to consider:**

| Use case | Domain | Why it matters | Data availability |
|---|---|---|---|
| | | | |

---

## 7. Security and compliance

| Question | Response |
|---|---|
| Zero-trust architecture in place for telemetry access? | Yes / Partial / No / Planned |
| PII masking at telemetry source? | Yes / Partial / No |
| Identity and policy framework | RBAC / OPA / Gatekeeper / Other: ___ / None |
| Data residency or sovereignty constraints | Yes (which regions: ___) / No |
| Regulatory frameworks that apply | _[free text]_ |
| Security observability spanning UE to RAN to Core to Cloud? | Yes / Partial / No |

---

## 8. Submission notes

| Field | Response |
|---|---|
| Sections left incomplete (list) | |
| Teams that need to be consulted for missing sections | |
| Preferred follow-up format | Call / Email / Async on wiki |
| Questions or concerns about this template | _[free text]_ |

---

_Template version: 1.0 -- LFN A-O/AI Working Group, D2 Observability Landscape Assessment_
_License: Apache 2.0_
