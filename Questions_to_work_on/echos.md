# Forward Deployed AI Engineer - Palantir Foundry
## Complete Interview Preparation Guide

**Prepared for:** Interview with Amit Gaba  
**Date:** July 7, 2026  
**Role:** Forward Deployed AI Engineer (Deloitte AI & Engineering - Palantir Practice)  
**Location:** Gurgaon / Bangalore (Hybrid)

---

## Table of Contents
1. [About the Role](#1-about-the-role)
2. [Interviewer Profile: Amit Gaba](#2-interviewer-profile-amit-gaba)
3. [Interview Structure & What to Expect](#3-interview-structure--what-to-expect)
4. [Foundational Palantir Foundry Concepts](#4-foundational-palantir-foundry-concepts)
5. [Use Case 1: Credit Risk Early Warning System - Banking](#5-use-case-1-credit-risk-early-warning-system)
6. [Use Case 2: AML / Fraud Network Detection - Banking](#6-use-case-2-aml--fraud-network-detection)
7. [Use Case 3: Claims Fraud Detection - Insurance](#7-use-case-3-claims-fraud-detection)
8. [Use Case 4: Predictive Maintenance - Manufacturing](#8-use-case-4-predictive-maintenance)
9. [GenAI / LLM Integration into Foundry](#9-genai--llm-integration-into-foundry)
10. [Coding & Technical Preparation](#10-coding--technical-preparation)
11. [Behavioral Questions (STAR Format)](#11-behavioral-questions)
12. [Questions to Ask the Interviewer](#12-questions-to-ask-the-interviewer)
13. [30-Day Study Plan](#13-30-day-study-plan)
14. [Key Resources](#14-key-resources)

---

## 1. About the Role

### What is a Forward Deployed AI Engineer?
An FDE is a hybrid role — part engineer, part consultant — embedded directly with clients to build and deploy AI solutions using Palantir Foundry. You translate ambiguous business problems into scalable data models and AI workflows.

### Key Expectations per the JD:
- **Palantir Foundry** expertise: Ontology design, Transforms/Code Workbooks, Operational Actions, Object Explorer
- **GenAI/LLM integration** into Foundry workflows
- **Python** proficiency (TypeScript/JavaScript a plus)
- **ML concepts**: prompt design, evaluation, fine-tuning
- **Client-facing**: ~25% travel, cross-functional communication
- **Builder's mindset**: ship real solutions, iterate fast
- **Industries**: OEM, BFSI (Banking, Financial Services, Insurance), and others

### What Deloitte Looks For Specifically:
- Experience deploying GenAI solutions in production
- End-to-end ownership from problem discovery to deployment
- Comfort with ambiguity — you won't have all the requirements upfront
- Ability to explain technical concepts to non-technical stakeholders

---

## 2. Interviewer Profile: Amit Gaba

Based on the LinkedIn profile provided: **Amit Gaba**

### What We Can Infer:
- Likely a senior leader/manager at Deloitte in the AI & Engineering / Palantir practice
- Based on the context, he's likely hiring for the Forward Deployed AI Engineer role
- He's shared specific use cases (Credit Risk, AML, Claims Fraud, Predictive Maintenance) — this tells us:
  - He has **deep domain knowledge** in BFSI and Manufacturing
  - He values **practical, hands-on problem solving** over theoretical knowledge
  - He wants to see how you think through **end-to-end solutions**

### What He Will Likely Evaluate:
1. **Technical depth** in Palantir Foundry
2. **Domain understanding** across BFSI and Manufacturing
3. **Communication clarity** — can you explain complex ideas simply?
4. **Problem decomposition** — given ambiguity, can you structure a solution?
5. **Cultural fit** — builder mindset, curiosity, pragmatism

### How to Impress Him:
- Speak in **Palantir-native vocabulary** (Ontology, Actions, Transforms, Writeback, Object Explorer, AIP)
- Connect every answer back to **real business outcomes**
- Show you understand the **"last mile" problem** — deploying AI that actually gets used
- Reference **specific use cases** from your research

---

## 3. Interview Structure & What to Expect

Based on research across FDE interviews at Deloitte/Palantir:

### Round 1: Recruiter Screen (30 min)
- Background, experience, motivation
- Why this role? Why Deloitte?
- Basic technical fit check

### Round 2: Technical Phone Screen (45-60 min)
- **Coding problem** (Python/SQL) — data manipulation, not LeetCode algorithms
- **Foundry concepts** — high-level understanding
- May include a mini case study

### Round 3: Onsite / Virtual Onsite (3-5 rounds)

#### A. Deployment Scenario / Case Study (most important!)
- Given a vague, real-world problem → you must scope, structure, and propose a solution
- **Example:** "A bank wants to identify customers who might default. Where do you start?"
- **What they test:** 
  - How you handle ambiguity
  - Your ability to ask clarifying questions
  - How you structure a phased approach
  - Trade-off awareness

#### B. Technical Deep-Dive
- **Ontology design** — given a business scenario, model the entities, relationships, and properties
- **Data pipeline design** — how would you ingest, transform, and serve data?
- **ML/GenAI integration** — how to embed LLMs into Foundry workflows

#### C. Coding Round
- **Python** — data processing, aggregation, error handling
- **SQL** — window functions, CTEs, data quality checks
- Write production-quality code (not just "passes tests")

#### D. Behavioral & Values
- STAR-format questions
- "Tell me about a time you dealt with ambiguity"
- "How do you handle a difficult stakeholder?"
- "What's a project you owned end-to-end?"

#### E. Client Simulation
- Role-play: you're with a client, they raise a concern or request
- How do you respond? Probe, diagnose, propose

---

## 4. Foundational Palantir Foundry Concepts

### The Ontology (Palantir's Superpower)
The Ontology is a **semantic layer** that sits between raw data and applications. Instead of tables, you work with business objects.

| Concept | Description |
|---------|-------------|
| **Object Type** | A real-world entity (Customer, Loan, Transaction, Equipment) |
| **Property** | Attributes of an object (credit_score, loan_amount, status) |
| **Link** | Relationship between objects (Customer → Loan, Equipment → MaintenanceEvent) |
| **Object Set** | Collection of objects of the same type |
| **Action** | An operation that modifies an object (Approve Loan, Flag Alert, Escalate) |

### Key Foundry Components

| Component | Purpose |
|-----------|---------|
| **Data Connection** | Ingests data from source systems (batch, streaming) |
| **Code Repository** | Git-based version control for transforms |
| **Transforms** | PySpark/SQL pipelines that clean, join, and prepare data |
| **Code Workbook** | Interactive Python/R/SQL environment for analysis |
| **Ontology Manager** | Define objects, links, actions, and permissions |
| **Object Explorer** | Search, browse, and explore ontology objects |
| **Workshop** | Build operational applications (dashboards, forms) |
| **Foundry Rules** | No-code rule builder for alerts |
| **AIP** | AI Platform — integrates LLMs with ontology for agentic workflows |
| **Apollo** | Deploy Foundry across cloud, on-prem, or air-gapped environments |
| **Contour** | Visual data exploration (drag-and-drop analytics) |

### The FDE Deployment Framework (5-Step)

```
1. DISCOVERY → 2. SCOPE → 3. BUILD → 4. DEPLOY → 5. ITERATE
```

**Step 1: Discovery (Days 1-2)**
- Stakeholder interviews: "What decisions feel slow? What info do you wish you had?"
- Data audit: What sources exist? How clean are they? What's feasible to integrate quickly?

**Step 2: Scope (Day 2)**
- Define a **"slice of value"** — the smallest useful thing you can deliver in Week 1
- Explicitly list what's IN scope and OUT of scope
- Get stakeholder buy-in on the plan

**Step 3: Build (Days 3-4)**
- Ingest data into Foundry
- Define ontology objects and links
- Build transforms for cleaning and enrichment
- Create Workshop app / Foundry Rules for alerts
- Wire up Actions for writeback

**Step 4: Deploy (Day 5)**
- Demo to stakeholders
- Collect feedback
- Measure impact

**Step 5: Iterate (Week 2+)**
- Refine models, add more data sources, expand scope
- Improve alert thresholds based on user feedback

### Ontology Design Principles
1. **Entity-first, not table-first** — model business concepts, not database tables
2. **Keep entities long-lived and meaningful** — don't create objects for transient data
3. **Use Links wisely** — 1:many vs many:many relationships have performance implications
4. **Interactive vs. Index-only** — if an object needs human edits, design for Actions
5. **Don't overload objects** — too many properties slow down queries
6. **Version and evolve** — ship a usable ontology quickly, then iterate

---

## 5. Use Case 1: Credit Risk Early Warning System - Banking

### The Problem
A bank wants to **proactively identify customers likely to default** before it happens. Currently they react after defaults occur.

### Key Questions to Answer
1. How would you model the data entities?
2. What early risk signals would you look for?
3. How would a risk officer consume this system?

### 5.1 Ontology Design

```
┌─────────────┐         ┌──────────────┐         ┌─────────────┐
│   Customer   │────────▶│    Loan      │────────▶│  Payment    │
│  (Object)    │ 1:m     │  (Object)    │ 1:m     │  (Object)   │
├─────────────┤         ├──────────────┤         ├─────────────┤
│ customer_id  │         │ loan_id       │         │ payment_id  │
│ name         │         │ customer_id   │         │ loan_id     │
│ credit_score │         │ amount        │         │ due_date    │
│ income       │         │ interest_rate │         │ paid_amount │
│ employment_st│         │ start_date    │         │ status      │
│ dti_ratio    │         │ tenure_months │         │ delay_days  │
│ num_accounts │         │ collateral    │         │ payment_date│
│ delinquency_h│         │ status        │         │             │
│              │         │ risk_score    │         │             │
└──────┬───────┘         └──────┬────────┘         └─────────────┘
       │                        │
       │                  ┌─────▼──────────┐
       │                  │  EarlyWarning  │
       └──────────────────▶  Alert         │
                          │  (Object)      │
                          ├───────────────┤
                          │ alert_id       │
                          │ customer_id    │
                          │ loan_id        │
                          │ risk_level     │
                          │ signal_type    │
                          │ generated_date │
                          │ reviewed_by    │
                          │ resolution     │
                          └───────────────┘
```

**Entity Details:**

| Object | Properties |
|--------|-----------|
| **Customer** | customer_id, name, credit_score, income, employment_status, dti_ratio, num_accounts, delinquency_history, segment |
| **Loan** | loan_id, customer_id, amount, interest_rate, start_date, tenure, collateral_value, status, current_risk_score |
| **Payment** | payment_id, loan_id, due_date, paid_amount, delay_days, status, payment_date |
| **EarlyWarning Alert** | alert_id, customer_id, loan_id, risk_level (Low/Med/High/Critical), signal_type, generated_date, reviewed_by, resolution |

**Key Links:**
- Customer 1:m Loan (one customer can have multiple loans)
- Loan 1:m Payment (each loan has payment history)
- Customer 1:m EarlyWarning Alert
- Loan 1:m EarlyWarning Alert

### 5.2 Early Risk Signals to Look For

**Behavioral Signals:**
1. **Payment pattern changes** — from full payment → minimum payment → missed payment
2. **Utilization spikes** — credit card balances increasing suddenly
3. **Cash advance behavior** — multiple cash advances in short period
4. **Delinquency drift** — 15-day → 30-day → 60-day overdue
5. **Borrowing from Peter to pay Paul** — new loans taken to pay old ones

**Financial Signals:**
6. **DTI ratio crossing threshold** — debt-to-income > 40-50%
7. **Employment changes** — frequent job switches, industry downturn
8. **Credit score drop** — significant decrease over 3-6 months
9. **New credit inquiries** — multiple hard inquiries (shopping for credit = distress)
10. **Collateral value decline** — property/asset backing loan losing value

**External Signals:**
11. **Macroeconomic indicators** — interest rate hikes, inflation
12. **Industry-specific** — sector downturn, regulatory changes
13. **Social sentiment** — negative news about employer or industry

**Composite Signals (ML-powered):**
14. **Payment shock prediction** — upcoming rate reset will increase EMI significantly
15. **Life event detection** — divorce, medical emergency, job loss (from transaction patterns)
16. **Cross-product risk** — customer is risky across products, not just one loan

### 5.3 How a Risk Officer Consumes This (Workshop App)

**Dashboard View (Landing Page):**
- Total alerts by risk level (Critical → High → Medium → Low)
- Trend chart: alerts generated vs. resolved over time
- Top 10 highest-risk customers (with drill-down)
- KPI cards: % reviewed, avg resolution time, prevented defaults

**Alert Queue (Prioritized):**
- Sorted by risk_level (Critical first) → generated_date (newest first)
- Each row shows: Customer Name, Loan ID, Risk Score, Signal Type, Days Since Alert
- Color-coded: Red (Critical), Orange (High), Yellow (Medium), Blue (Low)

**Customer 360 View (Drill-down):**
When the officer clicks a customer:
- **Summary**: Credit score trend, DTI ratio, income, employment
- **Loan Portfolio**: All active loans with statuses
- **Payment History**: Timeline of payments vs. due dates
- **Recent Activity**: Transactions, inquiries, account changes
- **Alert History**: Previous alerts and resolutions

**Decision Actions:**
- **Contact Customer** (log call/email)
- **Escalate** (send to senior risk team)
- **Restructure Loan** (suggest repayment plan)
- **Mark as Reviewed - No Action Needed**
- **Close Alert**

**Writeback:**
Every action is recorded via Ontology Actions, creating a feedback loop:
- Actions update the `EarlyWarningAlert` object (reviewed_by, resolution, notes)
- Feedback improves the alert model
- Data flows back to core banking systems via writeback

### 5.4 How to Answer in the Interview

```
"To build a Credit Risk Early Warning System in Foundry, I'd start by
spending Day 1 with the risk team to understand their current process and
pain points. I'd ask: 'What information do you wish you had 30 days before
a default?' and 'What decisions do you make today with incomplete data?'

For the ontology, I'd model four core objects: Customer, Loan, Payment, and
EarlyWarningAlert. Customer links to Loan (1:m), Loan links to Payment (1:m),
and alerts are generated against Customers and Loans.

For early signals, I'd look at three categories: behavioral signals like
payment pattern changes and utilization spikes; financial signals like DTI
ratio crossing thresholds and credit score drops; and external signals like
macroeconomic indicators. In Phase 1, I'd start with rule-based signals
using Foundry Rules for quick wins. Phase 2 would add ML-based composite
signals using a gradient boosting model deployed via Code Workbooks.

For the risk officer, they'd get a Workshop app with a prioritized alert queue,
Customer 360 drill-down, and one-click Actions for writeback. Every decision
they make feeds back into the model, creating a continuous improvement loop.

The success metric would be: how many days earlier we can identify a
potential default compared to the current process, measured by the shift
from reactive to proactive intervention."
```

---

## 6. Use Case 2: AML / Fraud Network Detection - Banking

### The Problem
Bank is under regulatory pressure for **missing suspicious activity patterns**. Currently using rule-based monitoring with high false positives (98%+ false positive rate is common).

### Key Questions to Answer
1. How to identify hidden fraud networks?
2. How to reduce false positives?
3. How would investigators interact with the system?

### 6.1 Ontology Design for Network Detection

```
┌──────────────┐     ┌──────────────────┐     ┌───────────────┐
│   Customer    │────▶│   Account        │────▶│  Transaction  │
│  (Object)     │ 1:m │  (Object)        │ 1:m │  (Object)     │
├──────────────┤     ├──────────────────┤     ├───────────────┤
│ customer_id   │     │ account_id        │     │ tx_id          │
│ name          │     │ customer_id       │     │ from_account   │
│ address       │     │ account_type      │     │ to_account     │
│ id_docs       │     │ open_date         │     │ amount         │
│ risk_score    │     │ balance           │     │ timestamp      │
│ kyc_status    │     │ status            │     │ type           │
│ pep_flag      │     │ risk_level        │     │ channel        │
│ sanctions_flag│     │                   │     │ location       │
└──────┬────────┘     └──────────────────┘     └───────┬────────┘
       │                                               │
       │      ┌─────────────────────┐                  │
       │      │   SuspiciousAlert   │                  │
       └──────▶   (Object)          │◄─────────────────┘
              ├─────────────────────┤
              │ alert_id            │
              │ customer_id         │
              │ tx_id(s)            │
              │ risk_score          │
              │ pattern_type        │
              │ generated_date      │
              │ investigator        │
              │ status (open/closed)│
              │ disposition         │
              └─────────────────────┘
```

**Additional Objects for Network Detection:**

| Object | Purpose |
|--------|---------|
| **BeneficialOwner** | Links customers to entities they control |
| **SharedAttribute** | Phone, email, IP address, device ID shared across customers |
| **Counterparty** | External entities transacting with bank customers |
| **NetworkCluster** | Group of customers/devices/counterparties operating together |

### 6.2 How to Identify Hidden Fraud Networks

**Graph-Based Analysis:**

1. **Link Analysis** — Who transacts with whom? Build a directed graph of transactions
   - Look for **circular flows** (A→B→C→A) — classic money laundering
   - Look for **star patterns** (one account receives from many, sends to few)
   - Look for **bipartite patterns** (mules collecting from many senders)

2. **Entity Resolution** — The real challenge
   - "John Smith" at one branch ≠ same as "Jon Smith" at another branch?
   - Use Foundry's Entity Resolution to merge identities across:
     - Same phone number with different names
     - Same IP address with different accounts
     - Shared device fingerprints
     - Shared address with different family names

3. **Temporal Pattern Detection**
   - **Smurfing** — multiple small transactions just below reporting threshold (₹10L / $10K)
   - **Rapid movement** — funds flowing in and out quickly (layering)
   - **Structuring** — breaking large amounts into smaller deposits at different branches
   - **Strange hour activity** — transactions at 2 AM from accounts that normally transact at 10 AM

4. **ML-Based Anomaly Detection**
   - Train an autoencoder on normal transaction behavior
   - Flag transactions with high reconstruction error
   - Feature: amount, frequency, counterparty diversity, time-of-day, channel
   - Use graph neural networks (GNNs) for relationship-based fraud detection

### 6.3 How to Reduce False Positives

**Current problem:** 98%+ false positive rate means investigators waste time.

**Strategy to reduce FPs:**

1. **Tiered Alert Scoring:**
   - Tier 1 (Automated Rules) — High volume, high FP → score transactions
   - Tier 2 (ML Model) — Medium volume, medium FP → re-rank by risk score
   - Tier 3 (Network Analysis) — Low volume, low FP → only the strongest signals

2. **Feature Engineering:**
   - Add customer **baseline profiling** (what's "normal" for THIS customer?)
   - Add **behavioral drift tracking** (has this customer's pattern changed?)
   - Add **contextual features** (day of week, holiday calendar, known events)

3. **Feedback Loop (Writeback):**
   - Every "false positive" marked by investigator → feeds back into model
   - Model learns: "this pattern looked suspicious but was actually legitimate"
   - Continuous retraining reduces FP rate over time

4. **Business Rule Tuning:**
   - Foundry Rules allows analysts to tweak thresholds without code
   - Add exclusion lists for known patterns (e.g., seasonal business flows)

### 6.4 Investigator Interaction (Workshop App)

**Workbench Layout:**

1. **Dashboard** — Alert volume, clear rate, SARs filed, response time
2. **Alert Queue** — Prioritized by risk score, with context:
   - Customer profile, transaction summary, network graph
   - Similar past cases (pattern matching)
3. **Graph Explorer** — Interactive network visualization
   - Nodes = customers/accounts, Edges = transactions
   - Size = transaction volume, Color = risk level
   - Click a node to see full profile and connected entities
4. **Timeline View** — Chronological flow of transactions
5. **Case Management** — Build a case with supporting evidence
   - Drag transactions into a "case folder"
   - Add notes, attach documents
   - Generate SAR (Suspicious Activity Report) pre-form with all data
6. **Actions:**
   - **Not suspicious** (feedback to model)
   - **Flag for monitoring** (add to watchlist)
   - **Escalate** (send to senior investigator)
   - **File SAR** (generates regulatory report)

### 6.5 How to Answer in the Interview

```
"For AML network detection, the key insight is that fraudsters don't operate
in isolation — they form networks. In Foundry, I'd model this by creating
ontology objects for Customer, Account, Transaction, and critically,
NetworkCluster and SharedAttribute.

Entity resolution is the first battle. I'd use Foundry's Entity Resolution
to match customers across accounts, devices, IPs, and phones. This reveals
hidden connections that traditional AML systems miss.

For false positive reduction, I'd implement a three-tier system: automated
rules for initial screening, an ML model for risk scoring and prioritization,
and network analysis for only the strongest signals. The critical component
is the feedback loop — every time an investigator marks something as
legitimate, that data feeds back to retrain the model.

The investigator would get a Workshop app with a graph explorer showing
connections, a timeline view for transaction patterns, and one-click case
building. The key action is filing a SAR directly from Foundry — all
supporting evidence is automatically compiled.

Success is measured by: SAR quality scores improving, false positive rate
dropping month-over-month, and time-to-investigation decreasing."
```

---

## 7. Use Case 3: Claims Fraud Detection - Insurance

### The Problem
Auto insurance claims show signs of **organized fraud**. Need to detect fraudulent networks, prioritize investigations, and measure success.

### Key Questions to Answer
1. How to analyze relationships between claims?
2. How to prioritize investigations?
3. How to measure success?

### 7.1 Ontology Design

```
┌──────────────┐     ┌──────────────────┐     ┌─────────────────┐
│   Policy      │────▶│   Claim          │────▶│   Vehicle       │
│  (Object)     │ 1:m │  (Object)        │ 1:1 │  (Object)       │
├──────────────┤     ├──────────────────┤     ├─────────────────┤
│ policy_id     │     │ claim_id          │     │ vin              │
│ customer_id   │     │ policy_id         │     │ make_model       │
│ coverage_type │     │ claim_date        │     │ year             │
│ premium       │     │ amount_claimed    │     │ owner_history    │
│ start_date    │     │ amount_paid       │     │ accident_history │
│ status        │     │ status            │     │                  │
│               │     │ incident_type     │     └─────────────────┘
└──────┬────────┘     │ location          │
       │              │ description       │
       │              │ investigator_id   │
       │              └────────┬──────────┘
       │                       │
       │              ┌────────▼──────────┐     ┌─────────────────┐
       │              │  ClaimAlert       │     │  InvolvedParty  │
       └──────────────▶  (Object)         │     │  (Object)       │
                      ├──────────────────┤     ├─────────────────┤
                      │ alert_id          │     │ party_id         │
                      │ claim_id          │     │ claim_id         │
                      │ fraud_score       │     │ name             │
                      │ signal_type       │     │ role (driver,    │
                      │ generated_date    │     │      witness,    │
                      │ reviewed_by       │     │      shop)       │
                      │ disposition       │     │ phone            │
                      └──────────────────┘     │ address          │
                                                └─────────────────┘
```

**Additional Network Objects:**

| Object | Purpose |
|--------|---------|
| **RepairShop** | Tracks shops involved in claims — fraud rings often use the same shop |
| **MedicalProvider** | Same clinic treating multiple claimants from separate accidents |
| **RentalCarAgency** | Often colludes with repair shops to inflate claims |
| **ClaimCluster** | Group of claims linked by shared parties, locations, or timing |

### 7.2 Analyzing Relationships for Fraud Detection

**Red Flags in Relationships:**

1. **Same players, different accidents:**
   - Same repair shop appears in 20+ "unrelated" accidents
   - Same witness appears in multiple accidents
   - Same doctor/treatment center for different claimants
   - Same lawyer represents multiple claimants from different accidents

2. **Shared attributes across claims:**
   - Same phone number for different claimants
   - Same IP address filing multiple claims
   - Same address used by different policyholders
   - Same vehicle VIN appearing in multiple claims (staged accidents)

3. **Temporal-spatial clustering:**
   - Multiple claims within same zip code in short time window
   - Same intersection/corner generating many accidents
   - Claims filed just before policy cancellation/lapse

4. **Behavioral signals:**
   - Policy purchased just days before accident (30-day wait period evasion)
   - Late-night accident reporting
   - Inconsistent statements across parties
   - Claimant overly eager to settle quickly
   - Reluctance to share medical records

### 7.3 Prioritization Framework

**Score = f(Urgency, Impact, Confidence)**

| Factor | Weight | Elements |
|--------|--------|----------|
| **Urgency** | 30% | Is statute of limitations approaching? Is evidence time-sensitive? |
| **Impact** | 40% | Claim amount, network size, repeat offender probability |
| **Confidence** | 30% | Strength of signals, pattern match to known fraud rings |

**Tier System:**
- **Tier 1 (Investigate Now):** Score 80-100, clear network indicators, high-value
- **Tier 2 (Investigate Soon):** Score 60-80, moderate signals, medium value
- **Tier 3 (Monitor):** Score 40-60, interesting but insufficient evidence
- **Auto-Approve:** Score < 40, low risk, straight-through processing

### 7.4 How Success is Measured

| Metric | Formula | Target |
|--------|---------|--------|
| **Detection Rate** | Fraud identified / Total fraud in portfolio | >80% |
| **Precision** | True fraud alerts / Total alerts | >40% (industry avg ~10%) |
| **Time to Detection** | Date of fraud occurrence → date flagged | <30 days |
| **Recovery Rate** | Amount recovered / Amount paid on fraudulent claims | >50% |
| **Net Savings** | Fraud prevented + recovered - investigation cost | Positive ROI |
| **False Positive Rate** | False alerts / Total alerts | <60% (industry avg ~90%) |
| **Investigator Productivity** | Claims reviewed per day per investigator | 2-3x improvement |

### 7.5 How to Answer in the Interview

```
"For insurance claims fraud, the ontology is critical. I'd model Policy,
Claim, Vehicle, InvolvedParty, RepairShop, and ClaimCluster objects. The
key insight is that organized fraud leaves a pattern — the same network of
shops, lawyers, and providers appearing across seemingly unrelated claims.

Foundry's Entity Resolution would link claims by shared phone numbers,
addresses, vehicle VINs, and IP addresses to surface hidden connections.
In the Workshop app, investigators would see a network graph of connected
claims and drill into specific relationships.

For prioritization, I'd use a composite score: 30% urgency, 40% impact,
30% confidence. This ensures investigators focus on the highest-value,
most-confirmed cases first, rather than chasing low-signal alerts.

Success is measured by four things: detection rate improving over time,
false positive rate declining (powered by the feedback loop), time-to-detection
decreasing, and net savings — actual dollars recovered minus investigation cost.

In Foundry, every investigator action writes back to the ontology, creating
a continuous learning loop. Over time, the model gets better at distinguishing
organized fraud from legitimate claims, and the system adapts to new fraud
patterns as they emerge."
```

---

## 8. Use Case 4: Predictive Maintenance - Manufacturing

### The Problem
Unplanned downtime is causing major financial losses. Need to predict equipment failure before it happens and operationalize maintenance.

### Key Questions to Answer
1. How to predict equipment failure?
2. How to avoid false alarms?
3. How does this change daily plant operations?

### 8.1 Ontology Design

```
┌────────────────┐     ┌──────────────────┐     ┌──────────────────┐
│   Equipment     │────▶│   SensorReading  │     │   Maintenance    │
│  (Object)       │ 1:m │  (Object)        │     │   Record         │
├────────────────┤     ├──────────────────┤     │  (Object)        │
│ equipment_id    │     │ reading_id        │     ├──────────────────┤
│ equipment_type  │     │ equipment_id      │     │ maint_id          │
│ location        │     │ timestamp         │     │ equipment_id      │
│ install_date    │     │ temperature       │     │ scheduled_date    │
│ manufacturer    │     │ vibration         │     │ actual_date       │
│ model           │     │ pressure          │     │ maint_type        │
│ criticality     │     │ rpm               │     │ cost              │
│ status          │     │ power_consumption │     │ downtime_hrs      │
│                  │     │                  │     │ technician_id     │
└────────┬────────┘     └──────────────────┘     └──────────────────┘
         │                        │
         │               ┌────────▼──────────┐     ┌──────────────────┐
         │               │  FailurePrediction│     │  WorkOrder       │
         │               │  Alert            │     │  (Object)        │
         └───────────────▶  (Object)         │────▶├──────────────────┤
                         ├──────────────────┤     │ work_order_id     │
                         │ alert_id          │     │ equipment_id      │
                         │ equipment_id      │     │ alert_id          │
                         │ failure_probability│    │ created_date      │
                         │ predicted_ttf_days │     │ priority          │
                         │ signal_type       │     │ assigned_to       │
                         │ model_version     │     │ status            │
                         │ generated_date    │     │ completion_date   │
                         │ disposition       │     │ resolution        │
                         └──────────────────┘     └──────────────────┘
```

### 8.2 How to Predict Equipment Failure

**Approach: Hybrid (Rules + ML)**

**Phase 1 — Rule-Based (Quick Wins):**
- Temperature exceeding threshold (e.g., >85°C on motor bearing)
- Vibration above ISO 10816 severity limits
- Pressure drop across filters (clogging indicator)
- Runtime since last maintenance exceeding recommended interval
- Rapid change in power consumption (efficiency loss)

**Phase 2 — ML-Based (Sophisticated):**

*Types of models:*
1. **Remaining Useful Life (RUL) Regression** — Predict days until failure
   - Features: sensor readings, maintenance history, age, load cycles
   - Model: Gradient Boosting, Random Forest, or LSTM for time series

2. **Anomaly Detection** — Flag abnormal sensor patterns
   - Train an autoencoder on "healthy" operation data
   - Flag when reconstruction error exceeds threshold
   - Catches novel failure modes never seen before

3. **Multi-Sensor Fusion** — Combine signals across sensors
   - Vibration + temperature + pressure together tell a story
   - A change in one sensor might be noise; change in 3 sensors = signal

**Feature Engineering:**
```
Rolling Window Features (last 24h, 7d, 30d):
  - avg_temp, max_temp, temp_std
  - vibration_peak, vibration_rms
  - pressure_drop_rate
  - power_consumption_trend (slope over time)
  - runtime_since_last_maintenance
  - cycles_since_last_maintenance
  - ambient_temperature (contextual)
  - load_factor (current load / rated capacity)
```

### 8.3 How to Avoid False Alarms

This is the **#1 challenge** in predictive maintenance. False alarms cause operators to ignore the system entirely.

**Strategies:**

1. **Confidence threshold tuning:**
   - Start conservative (only alert at >85% confidence)
   - Gradually lower threshold as model proves itself
   - Use Foundry's Impact Tracker to measure precision/recall

2. **Multi-modal confirmation:**
   - Don't alert on a single sensor anomaly
   - Require 2+ independent signals before triggering alert
   - Example: temperature spike + vibration increase + efficiency drop

3. **Contextual filtering:**
   - Account for operating conditions (startup, shutdown, load changes)
   - A temperature spike during normal startup ≠ failure
   - Use time-series segmentation (steady-state vs. transient)

4. **Feedback loop:**
   - Every alarm disposition (false alarm vs. real) feeds back to model
   - Model learns: "this vibration pattern at startup is normal, not failure"
   - Continuous retraining reduces false alarm rate over time

5. **Tiered alerts:**
   - **Advisory (Low):** Something interesting, check when you can
   - **Warning (Medium):** Schedule maintenance in next 7 days
   - **Critical (High):** Stop equipment and investigate now

### 8.4 How This Changes Daily Plant Operations

**Before Predictive Maintenance:**
- Reactive: Fix equipment after it breaks
- Schedule-based: Replace parts on calendar regardless of condition
- Unplanned downtime: 5-10% of production time lost
- Large spare parts inventory "just in case"

**After Predictive Maintenance:**
- **Shift from reactive to proactive:**
  - Operators check the "Equipment Health" dashboard at start of shift
  - Green/Yellow/Red indicators show equipment status
  - Maintenance switches from "fix when broken" to "intervene when predicted"

- **Maintenance scheduling transformed:**
  - Maintenance team plans work around production schedule
  - Parts ordered just-in-time based on predicted failure window
  - Bundled maintenance: fix multiple issues during one downtime window

- **Operator workflows:**
  - Morning standup includes health dashboard review
  - Alerts trigger work order creation automatically (via Ontology Actions)
  - Work orders assigned to teams based on skill and availability
  - Completion of work updates the ontology (MaintenanceRecord, Equipment status)

- **Continuous improvement loop:**
  - Actual failure data vs. predicted failure → model retraining
  - Maintenance cost data → ROI calculations
  - Downtime tracking → quantify savings

### 8.5 Success Metrics

| Metric | Description |
|--------|-------------|
| **Unplanned Downtime Reduction** | % decrease in unplanned outages |
| **Mean Time Between Failures (MTBF)** | Increasing trend |
| **Maintenance Cost Reduction** | % reduction in emergency repair costs |
| **False Alarm Rate** | % of alerts that are false |
| **Prediction Lead Time** | How many days before failure we predict it |
| **Maintenance Schedule Compliance** | % of scheduled maintenance completed on time |
| **Spare Parts Inventory Turnover** | Reduced inventory costs |
| **Overall Equipment Effectiveness (OEE)** | Combined metric: availability × performance × quality |

### 8.6 How to Answer in the Interview

```
"For predictive maintenance in Foundry, I'd model the ontology around
Equipment, SensorReading, MaintenanceRecord, FailurePredictionAlert, and
WorkOrder objects. The key is linking real-time sensor data to historical
maintenance records to build a complete asset health picture.

For prediction, I'd use a hybrid approach. Phase 1: rule-based alerts using
Foundry Rules for known failure modes — temperature thresholds, vibration
limits, runtime intervals. Phase 2: ML models deployed via Code Workbooks
for Remaining Useful Life prediction and anomaly detection.

False alarms are the biggest risk. I'd implement three strategies:
multi-modal confirmation (require 2+ signals before alerting), contextual
filtering (account for operating conditions), and a continuous feedback loop
where every false alarm improves the model.

The operational transformation is the real value. Plant operators start their
shift checking an Equipment Health dashboard. Maintenance shifts from reactive
to predictive. Work orders are auto-generated from alerts. Production schedules
optimize around predicted maintenance windows.

Success is measured by unplanned downtime reduction, MTBF improvement, and
the system's ability to predict failures with enough lead time for planned
intervention — at least 7-14 days before failure."
```

---

## 9. GenAI / LLM Integration into Foundry

### How AIP (Artificial Intelligence Platform) Works

AIP integrates LLMs into Foundry's ontology layer, enabling **agentic AI workflows**:

```
User Query → AIP Logic → Ontology Context → LLM → Actions → Writeback
```

### Key Integration Patterns:

**1. Natural Language to Ontology Actions**
- User asks: "Show me all high-risk customers in Mumbai"
- AIP translates to an Object Explorer query on Customer objects
- Returns results with drill-down capabilities

**2. RAG (Retrieval Augmented Generation) over Business Data**
- User asks: "Why did this claim get rejected?"
- AIP retrieves relevant ontology objects (Claim, Policy, Incident)
- Sends them as context to the LLM
- Returns a grounded, data-backed explanation

**3. Automated Report Generation**
- LLM generates a risk assessment report by pulling data from multiple ontology objects
- Format: narrative + tables + charts
- User reviews and publishes

**4. Anomaly Explanation**
- AIP detects an anomaly via the ML pipeline
- LLM generates a natural language explanation: "This transaction was flagged because..."
- Investigator gets context, not just a number

**5. Code Generation for Transforms**
- User says: "Build a pipeline that joins customer data with transactions on ID"
- AIP generates the PySpark/SQL transform code
- User reviews, tests, and deploys

### Prompt Design for Foundry AIP

**Key considerations:**
- **Ontology-aware prompting** — reference object types, not table names
- **Grounding** — always provide relevant ontology context in the prompt
- **Action scoping** — constrain what the LLM can do (read-only vs. write)
- **Guardrails** — ontologies + permissions ensure the LLM only accesses authorized data

### Interview Talking Points

```
"On the GenAI side, I'd integrate LLMs into Foundry workflows through AIP.
The key pattern is: use the ontology as the semantic grounding layer so the
LLM operates on business objects, not raw tables. This makes the AI
understand context — it knows that a 'Customer' has 'Loans' and 'Payments'.

For prompt design, I focus on three things: grounding the LLM with relevant
ontology data, constraining outputs to JSON for machine consumption, and
building guardrails using Foundry's existing permission model.

The most impactful GenAI use case in Foundry is natural language querying
over the ontology — letting risk officers ask questions like 'Show me all
customers with payment delays exceeding 30 days' and getting instant answers
without writing SQL."
```

---

## 10. Coding & Technical Preparation

### Python Focus Areas

**Data Manipulation (most common):**
- pandas: groupby, merge, apply, window functions
- Handling missing data, duplicates, schema changes
- Writing production-quality code (error handling, logging, type hints)

**Sample Problem Patterns:**
```python
# Pattern 1: Entity aggregation from event stream
def aggregate_entity_features(events: List[Dict]) -> Dict[str, Dict]:
    """Aggregate per-entity metrics from unordered event stream."""
    pass

# Pattern 2: Time-series anomaly detection
def detect_window_anomalies(events: List[Tuple[int, float]], 
                           W: int, k: float, m: int = 5) -> List[bool]:
    """Flag anomalies relative to sliding window statistics."""
    pass

# Pattern 3: Data quality checks
def validate_pipeline_output(df: pd.DataFrame, expected_schema: Dict) -> List[str]:
    """Check schema compliance, null rates, row counts, duplicates."""
    pass
```

### SQL Focus Areas

**Key skills:**
- Window functions (ROW_NUMBER, LAG, LEAD, RANK)
- CTEs for readable multi-step queries
- Handling slowly changing dimensions (SCD Type 2)
- Data quality assertions

**Sample Pattern:**
```sql
-- Latest event per transaction, compute net amounts
WITH latest_event AS (
  SELECT *,
    ROW_NUMBER() OVER (
      PARTITION BY transaction_id 
      ORDER BY event_ts DESC
    ) AS rn
  FROM payment_events
)
SELECT 
  event_date, merchant_id,
  SUM(CASE 
    WHEN status = 'COMPLETED' THEN amount
    WHEN status IN ('REFUNDED', 'CHARGEBACK') THEN -amount
    ELSE 0 END
  ) AS net_amount
FROM latest_event 
WHERE rn = 1
GROUP BY event_date, merchant_id;
```

### Key Foundry Technical Concepts to Master

1. **Transforms** — PySpark/SQL pipelines in Code Repositories
   - Incremental vs. full builds
   - Input/output datasets
   - Schema evolution handling

2. **Code Workbooks** — Interactive Python/R/SQL environment
   - No equivalent in traditional tools
   - Used for exploration, model training, ad-hoc analysis

3. **Ontology Actions** — Writeback to production
   - Action types: create, update, delete objects
   - Validation rules and side effects
   - Integration with external systems via webhooks/APIs

4. **Object Storage** — How objects are indexed and served
   - Indexing strategies for performance
   - Query patterns that are efficient vs. expensive

5. **Contour** — No-code visual analytics
   - Drag-and-drop analysis
   - Useful for enabling business users to explore data

---

## 11. Behavioral Questions (STAR Format)

### Prepare 5 Core Stories

| Theme | Story You Need |
|-------|---------------|
| **Handling Ambiguity** | A time when requirements were unclear — how did you scope and deliver? |
| **Cross-Functional Collaboration** | Worked with non-technical stakeholders to solve a problem |
| **Technical Ownership** | A project you built end-to-end, from discovery to production |
| **Failure & Learning** | A project that went wrong — what did you learn? |
| **Difficult Stakeholder** | Disagreement with a client/manager — how did you resolve it? |

### Sample STAR Stories

**Q: "Tell me about a time you dealt with ambiguity."**

```
S: I was asked to build a risk monitoring system for a bank that had 
   'lots of data' but no clear requirements on what to monitor.
T: I needed to deliver something useful in 2 weeks despite not knowing 
   what signals mattered to the risk team.
A: I spent the first 2 days doing stakeholder discovery — meeting with 
   risk officers, understanding their daily workflow, and identifying 
   their top 3 pain points. I scoped a 'Week 1 slice': a dashboard 
   showing just payment delays > 30 days and credit score drops > 50 points. 
   I explicitly told stakeholders what was NOT in scope to manage expectations.
R: The team got value on Day 5 instead of Month 3. They identified 
   12 high-risk customers in the first week and we expanded the system 
   based on their feedback. The approach became the template for future 
   deployments.
```

**Q: "How do you handle a client who wants a feature that won't solve their real problem?"**

```
S: An insurance client insisted on building a complex real-time fraud 
   detection pipeline, but their investigators were spending 90% of time 
   on data collection, not analysis.
T: The client was passionate about 'real-time AI' but their actual 
   bottleneck was operational — getting data from 5 different systems 
   before they could even start investigating.
A: I ran a time-motion study showing 90% of investigator time was 
   data-gathering. I proposed a two-phase approach: Phase 1 — build a 
   unified data view in Foundry (2 weeks), Phase 2 — add ML-based alerts 
   (4 weeks). I framed it as 'let's fix the data access problem first, 
   then the AI will have clean data to work with.'
R: Phase 1 reduced investigation prep time by 70%. The client was thrilled 
   and Phase 2 was even more impactful because the ML model had clean, 
   integrated data. The relationship strengthened because I prioritized 
   their actual problem over their stated solution.
```

---

## 12. Questions to Ask the Interviewer

### Strategy & Team Questions
1. "What does the ideal first 30 days look like for someone in this role?"
2. "How do you balance the consulting side (client management) vs. the engineering side (building solutions)?"
3. "What industries are you currently deploying into, and what's the biggest challenge in each?"
4. "How does the feedback loop work between FDEs in the field and the product/engineering team?"
5. "What's the team culture like — do FDEs collaborate often, or work independently?"

### Technical Questions
6. "How mature is the GenAI/AIP integration into Foundry for your current clients?"
7. "What's the most technically challenging deployment your team has done?"
8. "How do you handle data sovereignty / compliance requirements across different clients?"
9. "What's the preferred tech stack for ML model deployment in Foundry?"
10. "How do you measure the success of an FDE engagement?"

### Career Growth Questions
11. "What does career progression look like for an FDE in this practice?"
12. "Are there opportunities to specialize in a particular industry or stay broad?"
13. "How does the ~25% travel play out in practice?"
14. "What's the most rewarding part of this role from your perspective?"

---

## 13. 30-Day Study Plan

### Week 1: Foundations (Days 1-7)
- [ ] **Palantir Learn** (learn.palantir.com) — Complete Foundry Fundamentals
- [ ] Read Palantir Foundry documentation on Ontology, Transforms, Actions
- [ ] Watch Palantir's AIP demo videos on YouTube
- [ ] Practice Python data manipulation (pandas groupby/merge/window)
- [ ] Practice SQL window functions and CTEs
- [ ] Read Palantir's engineering blog posts

### Week 2: Deep Dive into Use Cases (Days 8-14)
- [ ] Write out ontology designs for all 4 use cases (paper-first)
- [ ] For each use case, prepare a 5-minute answer framework
- [ ] Research real-world implementations of these use cases
- [ ] Practice explaining each use case OUT LOUD (to wall/friend)
- [ ] Read about Credit Risk modeling concepts
- [ ] Read about AML transaction monitoring concepts
- [ ] Read about Predictive Maintenance ML approaches

### Week 3: Case Study & Coding Practice (Days 15-21)
- [ ] Do 3-4 timed coding problems (data manipulation focus)
- [ ] Practice the **Deployment Scenario Framework** with a friend
- [ ] Record yourself answering a case study — review for clarity
- [ ] Learn about LLM integration patterns (RAG, prompt engineering)
- [ ] Practice explaining a technical concept to a non-technical person

### Week 4: Mock Interviews & Polish (Days 22-30)
- [ ] Full mock interview (all rounds, timed)
- [ ] Polish STAR stories for behavioral questions
- [ ] Prepare 3-5 questions for the interviewer
- [ ] Review all use case frameworks one more time
- [ ] Read Palantir's quarterly letter/blog for company context
- [ ] Final review: Ontology vocabulary, Foundry concepts, architecture patterns

### Daily Practice (throughout)
- 15 min: Explain one use case out loud
- 15 min: Coding practice (data manipulation)
- 10 min: Read Foundry documentation or blogs
- 5 min: Review ontology design principles

---

## 14. Key Resources

### Official Palantir Resources
| Resource | URL |
|----------|-----|
| Palantir Learn (courses) | [learn.palantir.com](https://learn.palantir.com) |
| Foundry Documentation | [palantir.com/docs/foundry](https://www.palantir.com/docs/foundry) |
| Developers Portal | [palantir.com/developers](https://www.palantir.com/developers) |
| Foundry Use Case Patterns (Alerting) | [Alerting Workflow Docs](https://www.palantir.com/docs/foundry/use-case-patterns/alerting-workflow) |
| Foundry Use Case Patterns (Investigation) | [Investigation & Cohorting Docs](https://www.palantir.com/docs/foundry/use-case-patterns/investigation-and-cohorting) |
| Foundry Entity Resolution | [palantir.com/foundry-entity-resolution](https://www.palantir.com/foundry-entity-resolution) |
| Foundry for AML Whitepaper | [palantir.com/assets/...](https://www.palantir.com/assets/xrfr7uokpv1b/1faMo2Wb4LJzUZNt3tOmTm/14cc66723edced7355e90c6ef1b56246/Foundry_for_AML.pdf) |

### Interview Prep Resources
| Resource | URL |
|----------|-----|
| FDE Interview Guide | [fde.academy](https://fde.academy/blog/forward-deployed-engineer-interview-questions) |
| Palantir FDE Guide (Data Interview) | [datainterview.com](https://www.datainterview.com/blog/palantir-forward-deployed-engineer-interview) |
| Definitive FDE Guide 2026 | [sundeepteki.org](https://www.sundeepteki.org/advice/the-definitive-guide-to-forward-deployed-engineer-interviews-in-2026) |
| Forward Deployed AI Engineer Guide | [sundeepteki.org](https://www.sundeepteki.org/advice/forward-deployed-ai-engineer) |
| Palantir Interview Process | [resumeadapter.com](https://www.resumeadapter.com/companies/palantir/interview-process) |
| Palantir Engineering Blog | [blog.palantir.com](https://blog.palantir.com) |
| Echo SA (GenAI for Foundry) | [echo-s.ai](https://echo-s.ai/) |

### Books / Courses (Optional)
- *Building Machine Learning Pipelines* — good for ML pipeline design
- *Designing Data-Intensive Applications* by Kleppmann — data systems thinking
- *Feature Engineering for Machine Learning* by Zheng & Casari

### Interview Tips Summary

1. **Always start with discovery** — "I'd spend Day 1 with stakeholders understanding their pain points."
2. **Scope before you build** — "In Week 1, I'd deliver a minimal slice of value..."
3. **Use Foundry vocabulary** — Ontology, Actions, Writeback, Transforms, Object Explorer
4. **Show tradeoff awareness** — "For Phase 1, we'd use rules for speed, then add ML in Phase 2."
5. **Feedback loops are key** — Every answer should end with "...and the feedback writes back to the model."
6. **Business outcomes, not features** — Don't say "I'd build a dashboard." Say "I'd reduce default detection time from 60 days to 7 days."
7. **Be conversational** — You're solving a problem with the interviewer, not performing for them.
8. **Ask clarifying questions** — The #1 mistake is jumping to a solution too fast.

---

**Good luck with your interview! You've got this. 🚀**
