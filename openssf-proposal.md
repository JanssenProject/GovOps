# **Proposal of Scope for Review by the OpenSSF Technical Advisory Council (TAC)**

## **1\. Working Group Overview**

**Proposed Working Group Name:**   
GovOps Working Group

**Proposed Lifecycle Stage:**  
☐ Sandbox (initial)

**Primary Focus Area:**  
GovOps is a framework to help open source software projects facilitate enterprise risk management, accountability and transparency.

---

## **2\. Motivation**

GovOps is a framework to help open source software projects facilitate enterprise **risk management**, **accountability** and **transparency**. At a high level, GovOps seeks to help humans govern **effectively**, **efficiently**, and at **scale** through traceable authorization pipelines.

Compliance standards like ISO 27001 and SOC 2 define the minimum level of technical diligence an organization must demonstrate to align with well known security best practices. Compliance standards require that controls are in place to limit access, data and information to authorized entities for legitimate purposes. In the past, the assessment procedures for these controls were manual and periodic. GovOps seeks to provide an authorization governance mechanism that is interoperable in the open source supply chain to help organizations continuously prove compliance.

In the mid-2000s, Identity Governance and Administration (IGA) frameworks emerged to help enterprises govern **human workforce access to enterprise applications**. IGA systems inventory users, assign roles, and map those roles to permissions, enabling periodic access reviews and compliance reporting. GovOps builds on this foundation but addresses a broader risk surface: cloud infrastructure, APIs, service-to-service interactions, cross-domain federation, and autonomous or semi-autonomous software agents. These machine-driven capability surfaces were not first-class design targets for traditional IGA systems.

IGA was designed to govern applications which implement role based access control (RBAC). Today's policy engines offer greater expressiveness then RBAC, but also introduce new governance challenges. As policies evolve from simple role mappings to condition-rich logic spanning multiple attributes, identity tokens, and graphs--the effective permission surface becomes too complex for IGA-style access certification. New abstractions, metrics, and analysis techniques are required to make modern policy ecosystems understandable and governable. Addressing this gap is a central motivation for GovOps.

Developing these new governance practices requires collaboration among experts, vendors, and open-source communities with deep experience in identity, authorization, and distributed systems. The motivation for forming the GovOps Working Group under the OpenSSF is to create shared frameworks, terminology, models, and operational best practices necessary for consistent authorization governance across multi-domain, distributed software environments.

---

## **4\. Objective**

The objective of GovOps is to define and operationalize **governance-as-ops**: a continuous, measurable, and accountable discipline that allows humans to understand, prioritize, and reduce software security risk at scale.

Specifically, GovOps aims to establish a governance framework that:

**1\. Makes Governance Continuous and Operational**  
Governance must move from periodic, checklist-driven reviews to real-time control loops. GovOps defines how policies, telemetry, identity signals, and enforcement points work together as an operational system — where governance decisions are informed by live data, not static attestations.

**2\. Governs Capabilities, Not Just Identities**  
Traditional IGA focuses on *who has which role*. GovOps expands the scope to *which actions are possible on which resources under which conditions*. This enables governance over modern risk surfaces such as APIs, cloud services, machine identities, and autonomous agents, where role alone is insufficient to describe risk.

**3\. Preserve Determinism While Increasing Expressiveness**  
GovOps promotes policy models that remain deterministic and analyzable even as they grow more expressive than RBAC. This ensures governance remains provable: decisions must be traceable to explicit policy logic, and the space of permitted actions must be bounded and reviewable.

**4\. Enable Formal Reasoning About Authorization Risk**  
A core objective is to standardize how organizations use formally defined, decidable policy languages to reason about authorization behavior across *all possible states*, not just individual access requests. Technologies such as Cedar — originally developed at Amazon and contributed to the Cloud Native Computing Foundation — demonstrate how policy can become analyzable infrastructure. GovOps defines the governance practices required to manage such policies responsibly at scale.

**5\. Make Risk Measurable and Comparable**  
GovOps seeks to define metrics that help humans prioritize remediation. Instead of asking only “Is this compliant?”, organizations should be able to ask:

* What high-impact capabilities exist?  
* Which are weakly governed?  
* Where does policy coverage not match risk exposure?

This enables leadership to allocate resources based on **risk reduction**, not audit cycles.

**6\. Establish Accountability Across Humans and Systems**  
When incidents occur, governance must support attribution: which policy allowed the action, which system enforced it, and which human or team owned that policy. GovOps promotes traceability across the full policy lifecycle — design, deployment, decision, and outcome.

**7\. Define Shared Models and Best Practices**  
Through collaboration in the OpenSSF GovOps Working Group, this initiative will produce common terminology, reference architectures, control objectives, and operational practices. These artifacts will help vendors, open-source projects, and enterprises implement interoperable, governance-grade authorization in distributed, multi-domain environments.

---

In short, the objective of GovOps is to transform governance from a retrospective audit function into a **forward-looking operational capability** — one that continuously aligns technical authorization behavior with human intent, risk tolerance, and organizational accountability.

---

## **5\. Scope**

### **In Scope**

The GovOps WG will:

* Define **conceptual frameworks** for governance of authorization and decision systems  
* Develop **metrics and measurement models** for policy coverage, risk, and effectiveness  
* Produce **reference architectures** for policy lifecycle management  
* Standardize **interoperable formats and specifications** that enable governance tooling  
* Coordinate with existing OpenSSF WGs and Projects where policy intersects software supply chain security, compliance, identity, and tooling.

### **Out of Scope**

The WG will **not**:

* Build production authorization engines or identity providers  
* Duplicate work of existing WGs focused on vulnerability disclosure, repositories, or secure coding, or compliance  
* Mandate specific vendors, policy approaches or enforcement technologies

---

## **4\. Relationship to Existing OpenSSF Initiatives**

| Existing Initiative | Relationship | Distinction |
| :---- | ----- | ----- |
| Global Cyber Policy WG | Complementary | Compliance is the minimum amount of security required to meet legal or business thresholds. Governance policies are a superset of compliance policies. Compliance alone is not sufficient for security. |
| Gamara Project | Complementary | The model and lexicon defined by Gamara will be very useful for GovOps |
| Supply Chain Integrity WG | Adjacent | GovOps defines policy and decision artifacts, not software provenance. |
| Best Practices WG | Complementary | GovOps defines operational governance, not coding practices. |
| AI/ML Security WG | Adjacent | GovOps applies governance concepts across AI agents but is not AI-specific. |

GovOps is a specific response to the need for formalization of a new practice and body of knowledge around governance. 

---

## **5\. Intended Deliverables**

### **Initial Deliverables (12 months)**

1. **GovOps Framework**  
   * Statement of intent, values, and design principles  
   * Definitions, principles, and operating model  
   * Control planes (e.g., governance, identity, visibility, event)  
2. **GovOps Metrics Model**  
   * What is measured: risk, transparency, accountability and other desired outcomes  
   * How are they measured: KPIs suitable for automation  
3. **Standards**  
   * Formats or protocols that are not covered by other standard bodies or open source efforts, but are necessary for governance interoperability.   
   * [**Cedar**](https://www.cedarpolicy.com/) **Policy Store Specification**  
     1. Would be the first, based on [Cedar RFC 101](https://github.com/cedar-policy/rfcs/pull/101), which is considered out-of-scope for the Cedar core standard.   
     2. Defines a portable, versioned, interoperable format for storing Cedar policies, schemas, entities, and issuer metadata.   
   * **Protobuf to Cedar Entity Mapping**  
     1. Policy schema alignment is necessary for cross-domain authorization policies. 

---

## **6\. Meeting Times**

| Effort | Meeting Times | Agenda / Mtg Notes | Git Repo | Slack Channel | Mailing List |
| :---- | :---- | :---- | :---- | :---- | :---- |
| Full WG  | First and third Weds of month at 8am PST |  |  |  |  |
| Cedar Policy Store | First Weds of the month at 10am PST  |  |  |  |  |
| Protobuf / Cedar Mapping | Third Weds of the month at 10am PST |  |  |  |  |
|  |  |  |  |  |  |

---

## **7\.** 

---

## **7\. Governance and Operations**

**Meeting Cadence:**  
Weekly, public

**Decision-Making Model:**  
Consensus-based, per OpenSSF norms

**Communication Channels:**

* GitHub repository (WG \+ project)  
* OpenSSF Slack channel  
* Public meeting notes and recordings

## **8\. Initial Participants and Community Support**

This proposal is supported by **at least three individuals from at least two organizations**.

| Name | Organization | Role / Interest |
| ----- | ----- | ----- |
| [Michael Schwartz](https://www.linkedin.com/in/nynymike) | Gluu | Proponent, Contributor |
| [Rohit Khare](https://www.linkedin.com/in/rohitkhare/) | Independent | Proponent, Contributor |
| [Amie Dsouza](https://www.linkedin.com/in/amie-amrita-dsouza-48b6537/) | Schwab | Contributor |
| [Dinesh Rajasekharan](https://www.linkedin.com/in/dineshrajasekharan/) | Amazon | Contributor |
| [Ravindra Neriyanuri](https://www.linkedin.com/in/ACoAAAARN2UB8NtUXyamGuRr52KppXTzVG2ltuo) | Independent | Contributor |
| [André Koot](https://www.linkedin.com/in/meneer/) | SonicBee | Contributor |
| [Bernard Diwakar](https://www.linkedin.com/in/bernarddiwakar/) | Intuit | Contributor |
| [Manoj Kumar](https://www.linkedin.com/in/teampax/) | Pax Identity | Contributor |
| [Kamal Govindaswamy](https://www.linkedin.com/in/kgswamy/) | Tueoris | Contributor |
| [Brandon González](https://www.linkedin.com/in/bggp/)  | Independent | Contributor  |
| [Darran Rolls](mailto:darran@identityinnovationlabs.com) | Independent | Contributor |

---

## **9\. TAC Sponsor**

**TAC Sponsor:**  
*TBD*

The TAC Sponsor agrees to:

* Support the creation of the GovOps WG  
* Attend WG meetings regularly  
* Request TAC approval for WG creation  
* Not necessarily hold a formal WG leadership role

---

## **10\. Requested TAC Action**

The proponents respectfully request that the TAC:

☐ Review the proposed GovOps WG scope  
☐ Confirm limited overlap with existing initiatives  
☐ Approve creation of the GovOps Working Group at Sandbox stage  
☐ Approve incubation of the Cedar Policy Store specification as the WG’s initial Project


