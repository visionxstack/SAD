# Systems Analysis and Design — Exam Study Notes
**Format:** 6 scenario-based questions, 30 marks total
**Focus:** Application of concepts to business scenarios, NOT pure memorization

> **How to use these notes:** For every topic below, don't just learn the definition — practice explaining *why* it matters and *how* you'd apply it if given a mini business scenario. Exam answers should follow the pattern: **Identify → Explain → Apply → Justify.**

---

## 1. Systems Analysis and Design (SAD) & Information Systems

### What is SAD?
Systems Analysis and Design is the process of studying a business problem, designing a computer-based solution, and implementing it — essentially figuring out **what** a system should do (analysis) and **how** it should do it (design).

### Benefits of Systems Analysis and Design
When answering "why should this business use SAD," draw from these:
- **Improved efficiency** – automates manual, repetitive tasks, reducing time and errors
- **Better decision-making** – accurate, timely, well-organized data supports management decisions
- **Cost reduction** – eliminates redundant processes, reduces paperwork and labour costs
- **Improved accuracy** – reduces human error compared to manual systems
- **Better customer service** – faster processing, fewer mistakes, quicker response times
- **Scalability** – system built to grow with the business
- **Competitive advantage** – faster, more reliable systems than competitors
- **Clear documentation** – makes future maintenance and upgrades easier

**Exam tip:** If given a scenario (e.g., a shop still using paper ledgers), pick 3–4 *relevant* benefits and explain how they specifically solve that business's problem — don't just list all of them.

### Improving Existing Business Systems
Look for these signs in a scenario that a system needs improvement:
- Duplicate data entry / data inconsistency
- Long processing/waiting times
- Frequent errors or lost records
- Difficulty retrieving information
- Poor communication between departments
- Inability to handle growing volume of transactions

**Approach to answer:** Identify the specific weakness described → explain the business impact → propose the SAD-based improvement (e.g., a centralized database, an automated order system, a web portal).

### Types of Information Systems
Know these and be ready to match one to a scenario:

| System Type | Purpose | Example Use |
|---|---|---|
| **TPS** (Transaction Processing System) | Records day-to-day routine transactions | POS sales, payroll, bank withdrawals |
| **MIS** (Management Information System) | Summarizes TPS data into reports for middle management | Weekly sales summary reports |
| **DSS** (Decision Support System) | Helps managers make semi-structured decisions using analysis/modeling | "What if" pricing/inventory decisions |
| **ESS/EIS** (Executive Support System) | High-level summarized data for strategic decisions by top executives | Company-wide performance dashboards |
| **OAS** (Office Automation System) | Supports day-to-day office communication/documentation | Email, word processing, scheduling |
| **ES/AI System** (Expert System) | Mimics human expert decision-making using rules/knowledge base | Medical diagnosis support, credit approval |
| **ERP** (Enterprise Resource Planning) | Integrates all departments (finance, HR, inventory) into one system | SAP, Oracle ERP |

### Selecting a Suitable Information System
When a scenario asks "which system should this business implement?":
1. Identify **who** needs the system (operational staff? middle managers? top execs?)
2. Identify **what decision or task** it supports (routine transaction vs. strategic planning)
3. Match to the correct IS type from the table above
4. Justify with reference to the scenario's specific need

---

## 2. System Design and Testing

### System Design Concepts
- **Input design** – how data enters the system (forms, screens, validation rules)
- **Output design** – how information is presented (reports, screens, printouts)
- **Database/file design** – how data is structured and stored
- **User interface design** – ease of use, navigation, accessibility
- **Process design** – logic/workflow of how inputs become outputs
- **Architecture design** – client-server, cloud-based, distributed, etc.

**Design principle to remember:** Good design should be user-friendly, reliable, secure, maintainable, and scalable.

### Importance of System Testing
Testing verifies the system works correctly **before** it goes live. Key reasons:
- Detects errors/bugs before deployment (cheaper to fix early than after launch)
- Confirms the system meets stated requirements
- Ensures reliability and reduces system failure risk
- Improves user confidence and satisfaction
- Prevents costly business disruptions (e.g., wrong billing, data loss)
- Validates security (protects against unauthorized access/data breaches)

### Types of Testing (know these — often asked to match to a scenario)
| Type | What it Checks |
|---|---|
| **Unit Testing** | Individual components/modules in isolation |
| **Integration Testing** | Modules working together correctly |
| **System Testing** | The complete, integrated system as a whole |
| **User Acceptance Testing (UAT)** | Whether the system meets user/business needs — done by actual end users |
| **Regression Testing** | Ensures new changes haven't broken existing features |

### Applying Design & Testing to Solve Business Problems
**Exam approach:** If a scenario describes a business facing errors, crashes, or user complaints:
1. Identify the likely *design flaw* (poor input validation, confusing UI, weak database structure)
2. Recommend the specific *design fix*
3. Recommend the *testing type* that would have caught/should catch this issue
4. Explain the benefit (fewer errors, better user trust, smoother operations)

---

## 3. Feasibility Study

A feasibility study determines whether a proposed system is **worth pursuing** before full development begins.

### The Four Main Types of Feasibility
| Type | Question It Answers | Practical Example |
|---|---|---|
| **Technical Feasibility** | Do we have the technology, hardware, software, and skills to build this? | Does the company have staff who know the required programming language, or servers to host the new system? |
| **Economic Feasibility** | Do the benefits outweigh the costs? (Cost-Benefit Analysis) | Will the new inventory system save more in reduced waste than it costs to build/maintain? |
| **Operational Feasibility** | Will the system work within the organization's day-to-day operations? Will staff/users accept it? | Will employees resist switching from paper forms to a digital app? |
| **Schedule Feasibility** | Can the system be completed within the required time frame? | Can the system launch before the busy holiday sales season? |

*(Some syllabi also mention Legal Feasibility — compliance with laws/regulations, e.g., data protection laws.)*

### Applying Feasibility to a Scenario
When asked "conduct a feasibility analysis for [scenario]":
- Go through **each** of the four types systematically
- For each, state a specific consideration drawn from the scenario (not generic)
- Conclude whether the project appears feasible overall, with justification

**Example mini-answer structure:**
> "Technically, the business would need to acquire POS hardware and train staff — feasible if a small budget is allocated. Economically, the reduction in stock loss (as evidenced in the scenario) should offset development cost within X months. Operationally, staff already use smartphones, so adoption risk is low. Schedule-wise, a 3-month timeline is realistic for a system of this scale."

---

## 4. System Development Methodologies

### Traditional vs. Modern (Agile) Methodologies

| Aspect | **Traditional (Waterfall/SDLC)** | **Modern (Agile/Iterative)** |
|---|---|---|
| **Approach** | Sequential, linear phases (Requirements → Design → Build → Test → Deploy) | Iterative, incremental — built in small cycles ("sprints") |
| **Flexibility** | Low — hard to go back once a phase is done; changes are costly | High — requirements can evolve throughout the project |
| **Risk Handling** | Risk discovered late (often only at testing stage) | Risk identified early and often, each iteration |
| **Development Speed** | Slower to see final product — full system delivered at the end | Faster delivery of working parts — usable features delivered every sprint |
| **Client Involvement** | Mainly at start (requirements) and end (delivery) | Continuous — client reviews and gives feedback each sprint |
| **Documentation** | Heavy, detailed documentation at each phase | Lighter documentation; working software prioritized |
| **Best suited for** | Projects with clear, stable, well-understood requirements | Projects with evolving or unclear requirements, need for speed to market |

Other methodologies worth knowing by name (for completeness):
- **Prototyping** – build a working model early to gather user feedback quickly
- **RAD (Rapid Application Development)** – fast development using prototypes and reusable components
- **Spiral Model** – combines iterative development with structured risk analysis at each cycle

### Applying This to a Scenario
When asked "which methodology should this business use?":
- Look for clues: *Are requirements clearly defined and unlikely to change?* → Traditional/Waterfall
- *Is the business in a fast-changing environment, needs quick releases, or requirements are unclear/evolving?* → Agile
- Always justify using **flexibility, risk, and speed** — the three lenses the syllabus explicitly highlights.

---

## 5. Process Modelling and Data Modelling

### Process Modelling
**Purpose:** To visually represent how a business process works — the flow of activities, decisions, and information within a system.

**Common tools:**
- **DFD (Data Flow Diagram)** – shows how data moves between processes, data stores, external entities
- **Flowcharts** – shows step-by-step logic/sequence of a process
- **Use Case Diagrams** – shows interactions between users (actors) and the system

**Why it matters:**
- Helps identify **bottlenecks** (steps that slow the process down, e.g., manual approval delays)
- Reveals **redundant or duplicate steps** (e.g., the same data entered twice in different departments)
- Improves understanding of **how information flows** between departments
- Provides a basis for redesigning a more efficient process

### Data Modelling
**Purpose:** To define what data the system needs to store, and how different pieces of data relate to each other.

**Common tools:**
- **ERD (Entity-Relationship Diagram)** – shows entities (e.g., Customer, Order, Product) and their relationships
- **Data Dictionary** – documents each data field, its type, size, and rules

**Why it matters:**
- Prevents **data redundancy** (same data stored in multiple unnecessary places)
- Ensures **data integrity/consistency** (relationships enforced correctly, e.g., an Order must belong to a valid Customer)
- Provides the foundation for building an efficient, well-structured database

### Applying to a Scenario
When a scenario describes an inefficient business process (e.g., "orders take 3 days to process due to manual paper handoffs between three departments"):
1. Recommend **process modelling** (e.g., DFD) to map the current flow and pinpoint the exact bottleneck
2. Recommend **data modelling** (e.g., ERD) if the issue involves data duplication or inconsistency across departments
3. Explain how removing the identified inefficiency (e.g., automating the handoff, centralizing the data) solves the business problem

---

## 6. Requirements Analysis

### Functional Requirements
Describe **what the system must do** — specific features, functions, and behaviors.
- Examples: "The system shall allow customers to place an order online," "The system shall generate a monthly sales report," "The system shall send an email confirmation after checkout."

### Non-Functional Requirements
Describe **how the system should perform** — quality attributes, not specific features.
- **Performance** – e.g., system must load pages within 2 seconds
- **Security** – e.g., passwords must be encrypted
- **Usability** – e.g., interface must be accessible to non-technical users
- **Reliability/Availability** – e.g., system must have 99.9% uptime
- **Scalability** – e.g., must support 10,000 concurrent users
- **Maintainability** – e.g., system must be easy to update

**Quick way to remember the difference:**
> Functional = **"What"** the system does.
> Non-functional = **"How well"** it does it.

### Importance of Requirements Gathering and Documentation
- Ensures the final system actually solves the real business problem (avoids building the wrong thing)
- Reduces costly rework and miscommunication later in development
- Provides a clear benchmark for testing ("did we meet the requirement?")
- Improves communication between stakeholders (business users) and developers
- Creates a reference/contract that manages scope and expectations

**Common requirements-gathering techniques** (useful to mention in scenarios):
- Interviews with stakeholders/users
- Questionnaires/surveys
- Observation of current processes
- Document analysis (existing reports, forms)
- Joint Application Development (JAD) workshops

### Applying to a Scenario
When given a business scenario and asked to identify requirements:
1. Read carefully and pull out **explicit needs** stated in the scenario → these are your functional requirements
2. Infer **quality expectations** implied by the context (e.g., "the business handles sensitive customer data" → security is a non-functional requirement) → these are your non-functional requirements
3. Present them clearly, ideally in a short list, each phrased as "The system shall/must..."

---

## Exam Strategy — Putting It All Together

Since this is a **scenario-based, application-focused** exam, structure every answer like this:

1. **Identify** – What SAD concept(s) does this scenario relate to? (e.g., feasibility, methodology choice, type of IS)
2. **Explain** – Briefly define the relevant concept in your own words
3. **Apply** – Connect it directly to details *given in the scenario* (use the business's actual context — don't answer generically)
4. **Justify** – Explain *why* your recommendation is the best fit, referencing benefits/trade-offs

### Quick Self-Check Before the Exam
- [ ] Can I list and explain the benefits of SAD in my own words?
- [ ] Can I match a business scenario to the correct type of Information System?
- [ ] Can I explain why testing matters and name the testing types?
- [ ] Can I run through all 4 feasibility types on a sample scenario?
- [ ] Can I compare Traditional vs Agile on flexibility, risk, and speed without notes?
- [ ] Can I explain the difference between process modelling and data modelling, and why each matters?
- [ ] Can I distinguish functional vs non-functional requirements and write them properly?
- [ ] Have I reviewed the specific examples/case studies from lectures and tutorials?

### Final Tips
- Practice with **past papers or sample scenarios** if available — timing yourself helps.
- Keep answers **concise but justified** — for 30 marks across 6 questions (~5 marks each), aim for focused, well-structured paragraphs rather than long essays.
- Always tie your answer back to the **specific business scenario** given — generic textbook answers lose marks in application-based exams.
