# **Proposal of Scope for Review by the OpenSSF Technical Advisory Council (TAC)**

## **1\. Working Group Overview**

**Proposed Working Group Name:**   
GovOps Working Group

**Proposed Lifecycle Stage:**  
☐ Sandbox (initial)

**Primary Focus Area:**  
Authorization Governance / Interoperable Policy Management and Analysis

---

## **2\. Motivation**

GovOps is a framework to help open source software projects and enterprises achieve **risk management**, **accountability**, and **transparency**. At a high level, GovOps seeks to help humans—whether maintainers, project stewards, or enterprise operators—govern **effectively**, **efficiently**, and at **scale** through traceable authorization pipelines.

Compliance standards like ISO 27001 and SOC 2 require that controls are in place to limit access, data and information to authorized entities for legitimate purposes. In the past, the assessment procedures for these controls were manual and periodic. GovOps seeks to provide an authorization governance mechanism that is interoperable in the open source supply chain to help organizations continuously prove compliance.

In the mid-2000s, Identity Governance and Administration (IGA) frameworks emerged to help enterprises govern **human workforce access to enterprise applications**. IGA systems inventory users, assign roles, and map those roles to permissions, enabling periodic access reviews and compliance reporting. GovOps builds on this foundation but addresses a broader risk surface: cloud infrastructure, APIs, service-to-service interactions, cross-domain federation, and autonomous or semi-autonomous software agents. These machine-driven capability surfaces were not first-class design targets for traditional IGA systems.

IGA was designed to govern applications which implement role based access control (RBAC). Today's policy engines offer greater expressiveness than RBAC, but also introduce new governance challenges. As policies evolve from simple role mappings to condition-rich logic spanning multiple attributes, identity tokens, and graphs--the effective permission surface becomes too complex for IGA-style access certification. New abstractions, metrics, and analysis techniques are required to make modern policy ecosystems understandable and governable. Addressing this gap is a central motivation for GovOps. GovOps elevates continuous access review and policy-driven assurance as the primary control, while preserving a defined role for attestation and certification where required by regulation or audit.

Open source projects and the organizations that consume them need shared, vendor-neutral governance models and interoperable policy formats so that authorization can be reasoned about and assured across the supply chain—from upstream projects to downstream adopters—without lock-in to proprietary tooling. GovOps, developed in the open under the OpenSSF, gives the ecosystem common frameworks and specifications (such as a portable policy store format) that any project or vendor can implement: maintainers can declare and version policy with minimal overhead, and downstream consumers can verify or reason about the authorization behavior of components they adopt. Enterprises can use the same artifacts to govern open source and hybrid deployments consistently.

Developing these new governance practices requires collaboration among experts, vendors, and open-source communities with deep experience in identity, authorization, and distributed systems. The WG welcomes participation from identity governance and IGA vendors, GRC and risk and compliance platforms, open source policy projects, and enterprises running hybrid human-and-machine governance. The motivation for forming the GovOps Working Group under the OpenSSF is to create shared frameworks, terminology, models, and operational best practices necessary for consistent authorization governance across multi-domain, distributed software environments.

---

## **3\. Objective**

The objective of GovOps is to define and operationalize **governance-as-ops**: a continuous, measurable, and accountable discipline that allows humans—in enterprises and in open source projects—to understand, prioritize, and reduce software security risk at scale, including across the supply chain and in federated, multi-project environments.

Specifically, GovOps aims to establish a governance framework that:

**1\. Makes Governance Continuous and Operational**  
Governance must move from periodic, checklist-driven reviews to real-time or event-driven control loops where operational data exists. GovOps defines how policies, telemetry, identity signals, and enforcement points work together so that governance decisions are informed by declarative statements, not static attestations alone.

**2\. Governs Capabilities, Not Just Identities**  
Traditional IGA focuses on *who has which role*. GovOps expands the scope to *which actions are possible on which resources under which conditions*. This enables governance over modern risk surfaces such as APIs, cloud services, machine identities, autonomous agents, and—for open source—release, build, and supply-chain boundaries, where role alone is insufficient to describe risk.

**3\. Preserve Determinism While Increasing Expressiveness**  
GovOps promotes policy models that remain deterministic and amenable to automated analysis even as they grow more expressive than RBAC. This ensures governance remains provable: decisions must be traceable to explicit policy logic, and the set of permitted actions must have a finite representation (or be finitely enumerable) so that it is reviewable.

**4\. Document Reasoning About Authorization Risk**  
A core objective is to standardize how organizations and open source projects use formally specified policy languages (with well-defined semantics) to reason about authorization behavior for well-defined analysis tasks—e.g., safety over a bounded entity set—not only for individual access requests, so that downstream consumers can verify or reason about the authorization behavior of components they adopt. Where policy is machine-readable and designed to support composition across the supply chain (with composition semantics, e.g., precedence or override, specified where needed), governance scales across projects and vendors. For policies and mechanisms that are not machine-analyzable, GovOps defines how to scope and standardize review procedures so governance remains consistent. 

**5\. Make Risk Measurable and Comparable**  
GovOps seeks to define metrics that help humans—in enterprises and in open source projects—prioritize remediation. Instead of asking only “Is this compliant?”, organizations and maintainers should be able to ask:
* What high-impact capabilities exist?  
* Which are weakly governed?  
* Where does policy coverage not match risk exposure (including in supply chain or release process)?

This enables leadership and project stewards to allocate effort based on **risk reduction**, not audit cycles alone.

**6\. Establish Accountability Across Humans and Systems**  
When incidents occur, governance must support attribution: which policy allowed the action, which system enforced it, and which human or team owned that policy. GovOps promotes traceability across the full policy lifecycle—design, deployment, decision, and outcome. In open source and federated contexts, where ownership can be diffuse (maintainers, orgs, foundations), GovOps supports accountability through explicit, auditable answers to who can publish, approve releases, or revoke access—so that authorization behavior remains transparent and reviewable by the community.

**7\. Define Shared Models and Best Practices**  
Through collaboration in the OpenSSF GovOps Working Group, this initiative will produce common terminology, reference architectures, control objectives, and operational practices. These artifacts will help vendors, open source projects, and enterprises implement interoperable, governance-grade authorization in distributed, multi-domain environments—enabling projects and maintainers to adopt governance-grade authorization with minimal overhead and making the authorization behavior of open source components transparent and verifiable to the ecosystem.

---

In short, the objective of GovOps is to transform governance from a retrospective audit function into a **forward-looking operational capability**—one that continuously aligns technical authorization behavior with human intent, risk tolerance, and accountability in both enterprises and the open source ecosystem.

---

## **4\. Scope**

### **In Scope**

The GovOps WG will:

* Define **conceptual frameworks** for governance of authorization and decision systems  
* Develop **metrics and measurement models** for policy coverage, risk, and effectiveness  
* Produce **reference architectures** for policy lifecycle management  
* Standardize **interoperable formats and specifications** that enable governance tooling  
* Coordinate with existing OpenSSF WGs and Projects where policy intersects software supply chain security, compliance, identity, and tooling.  
* Ensure frameworks and specifications are usable by open source projects and maintainers (e.g., declarative policy, minimal operational overhead) as well as by enterprises and GRC platforms.

GovOps outputs (metrics, evidence, control posture) are designed to be consumed by Governance, Risk and Compliance ("GRC") and risk management platforms so that authorization governance is a first-class, aggregatable control domain—not a replacement for enterprise GRC.

### **Out of Scope**

The WG will **not**:

* Build production authorization engines or identity providers  
* Duplicate work of existing WGs focused on vulnerability disclosure, repositories, or secure coding, or compliance  
* Mandate specific vendors, policy approaches or enforcement technologies

IGA and identity platforms may implement GovOps frameworks in a variety of ways; the WG does not prescribe product architecture or policy engine choice.

---

## **5\. Relationship to Existing OpenSSF Initiatives**

| Existing Initiative | Relationship | Distinction |
| :---- | ----- | ----- |
| IGA / Identity Governance vendors & practitioners | Complementary | GovOps frameworks and specs (policy store, schema, metrics) can be adopted by IGA and identity platforms to extend human-centric governance to machine identities and continuous policy; GovOps does not define or replace IGA workflows. |
| GRC / Risk & Compliance platforms | Complementary | GovOps defines authorization governance metrics and assurance outputs that GRC and risk platforms can aggregate; GovOps does not duplicate enterprise GRC but provides a standardized control domain for authorization that GRC can consume and map to existing frameworks. |
| Global Cyber Policy WG | Complementary | GovOps defines how to govern authorization policies and continuous assurance |
| Gamara Project | Complementary | The model and lexicon defined by Gamara will be used in GovOps |
| Supply Chain Integrity WG | Adjacent | GovOps defines policy and decision artifacts, not software provenance. |
| Best Practices WG | Complementary | GovOps defines operational governance, not coding practices. |
| AI/ML Security WG | Adjacent | GovOps applies governance concepts across AI agents but is not AI-specific. |

GovOps is a specific response to the need for formalization of a new practice and body of knowledge around authorization governance. 

---

## **6\. Intended Deliverables**

### **Initial Deliverables (12 months)**

1. **GovOps Framework**  
   * Statement of intent, values, and design principles  
   * Definitions, principles, and operating model  
   * Control planes (e.g., governance, identity, visibility, event), with specified inputs, outputs, and invariants so implementations can be checked against a single model  
   * Guidance or patterns for open source and supply-chain use cases (e.g., release and build governance, consumer-verifiable policy)  
   * The GovOps governance plane coordinates with identity systems (including IGA and identity providers) rather than replacing them; the identity plane remains the domain of those systems.  
   * Control objectives and metrics are designed to be mappable to common control frameworks (e.g., NIST CSF, ISO 27001, SOC 2) so authorization governance can be reported alongside other domains in GRC and audit contexts.  
2. **GovOps Metrics Model** 
   * What is measured: risk, transparency, accountability and other desired outcomes  
   * How are they measured: KPIs suitable for automation (each metric defined as a function from observables to values, where applicable)  
   * At least one metric (e.g., transparency) given a concrete, formal definition to ensure automation and interoperability  
   * The model is designed to integrate with or extend existing governance and IGA metrics so enterprises can maintain a unified view across governance, risk, and compliance reporting rather than replacing current reporting.  
   * Metrics and KPIs are defined so they can be adopted by open source projects and maintainers (e.g., for release and supply-chain risk) as well as by enterprises.  
   * Where applicable, metrics and evidence align with or can be expressed in formats that GRC and compliance frameworks consume (e.g., OSCAL, Gamara or mappable control objectives).  
3. **Standards**  
   * **Cedar Policy Store Specification**
     1. [Cedar RFC 101](https://github.com/cedar-policy/rfcs/pull/101)—Defines a portable, versioned, interoperable format for storing Cedar policies, schemas, entities, and issuer metadata. The Policy Store spec defines representation and interchange only; authorization evaluation semantics remain defined by the underlying policy language (e.g., Cedar).   
   * **Govops Schema**  
     1. Standards for defining authorization policy schemas—entities, entity properties, actions, and resources—so policies are interoperable and analyzable.  
   * Composition semantics (e.g., how policies from multiple sources are combined or overridden) to be specified where needed, or explicitly scoped as future work.  

   The policy store and schema work are intended to inform or align with other policy representations over time, so the WG remains inclusive of implementations using other policy engines.

---

## **7\. Meeting Times**

| Effort | Meeting Times | Agenda / Mtg Notes | Git Repo | Slack Channel | Mailing List |
| :---- | :---- | :---- | :---- | :---- | :---- |
| Full WG  | First and third Weds of month at 10am PST | TBD | TBD | TBD | TBD |
| Cedar Policy Store Group | First Weds of the month at 12pm PST  | TBD | TBD | TBD | TBD |
| Schema Group | Third Weds of the month at 12pm PST | TBD | TBD | TBD | TBD |
|  |  |  |  |  |  |

---


## **8\. Governance and Operations**

**Meeting Cadence:**  
Bi-weekly (first and third Wednesday), public

**Decision-Making Model:**  
Consensus-based, per OpenSSF norms

**Communication Channels:**

* GitHub repository (WG \+ project)
* OpenSSF Slack channel
* Linkedin Group (which has stronger identity proofing)
* Public meeting notes and recordings

## **9. Initial Participants and Community Support**

This proposal is supported by **at least three individuals from at least two organizations**.

| Name | Organization | Role / Interest |
| ----- | ----- | ----- |
| [Michael Schwartz](https://www.linkedin.com/in/nynymike) | Gluu | Proponent, Contributor |
| [Rohit Khare](https://www.linkedin.com/in/rohitkhare/) | Independent | Proponent, Contributor |
| [Darran Rolls](mailto:darran@identityinnovationlabs.com) | Independent | Contributor |
| [Dinesh Rajasekharan](https://www.linkedin.com/in/dineshrajasekharan/) | Amazon | Contributor |
| [Dhaval Desai](https://www.linkedin.com/in/dhavaltdesai/) | Gluu | Contributor | 
| [André Koot](https://www.linkedin.com/in/meneer/) | SonicBee | Contributor |
| [Amie Dsouza](https://www.linkedin.com/in/amie-amrita-dsouza-48b6537/) | Independent | Contributor |
| [Bernard Diwakar](https://www.linkedin.com/in/bernarddiwakar/) | Intuit | Contributor |
| [Manoj Kumar](https://www.linkedin.com/in/teampax/) | Pax Identity | Contributor |
| [Kamal Govindaswamy](https://www.linkedin.com/in/kgswamy/) | Tueoris | Contributor |
| [Ravindra Neriyanuri](https://www.linkedin.com/in/ACoAAAARN2UB8NtUXyamGuRr52KppXTzVG2ltuo) | Independent | Contributor |
| [Brandon González](https://www.linkedin.com/in/bggp/)  | Independent | Contributor  |

---

## **10. TAC Sponsor**

**TAC Sponsor:**  
*TBD*

The TAC Sponsor agrees to:

* Support the creation of the GovOps WG  
* Attend WG meetings regularly  
* Request TAC approval for WG creation  
* Not necessarily hold a formal WG leadership role

---

## **11. Requested TAC Action**

The proponents request that the TAC approve the GovOps Working Group at Sandbox stage and endorse incubation of the Cedar Policy Store specification as the WG’s first deliverable:

☐ Review the proposed GovOps WG scope  
☐ Confirm limited overlap with existing initiatives  
☐ Approve creation of the GovOps Working Group at Sandbox stage  
☐ Approve the Cedar Policy Store specification as the WG’s first deliverable—a specification produced and maintained by the GovOps WG itself, not a separate OpenSSF Project.

---

## **12. References**

* [GovOps Github Organization](https://github.com/GovOpsWG)
* [GovOps Linkedin Group](https://www.linkedin.com/groups/17478011/)
* Cedar Policy Store draft specification: [https://gluu.co/rfc-101](https://gluu.co/rfc-101)

**GovOps Medium series (Gluu):**

* [Introducing GovOps](https://gluufederation.medium.com/introducing-govops-02063b72db4b)  
* [GovOps Manifesto](https://gluufederation.medium.com/govops-manifesto-33eb7cb01ed3)  
* [Risk, Transparency, and Accountability: The Core Metrics of GovOps](https://gluufederation.medium.com/risk-transparency-and-accountability-the-core-metrics-of-govops-ff09c9ffb76b)  
* [GovOps upgrades Access Certification to Access Review](https://gluufederation.medium.com/govops-upgrades-access-certification-to-access-review-2962c3dbf91f)  
* [Enterprise Security needs Brains, Body, Eyes, and Muscles](https://gluufederation.medium.com/enterprise-security-needs-brains-body-eyes-and-muscles-cae7bd25e3e9)


