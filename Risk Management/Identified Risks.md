# Introduction

**Version:** 2.1

**Last Edit:** 04.05.2025

**Last Editor:** Kirill Korikov

**Owner:** Yaroslav Kim

**Approval Status:** N/A

**Type:** Documentation

**Description:** This document describes potential project risks and ways to mitigate them.

**Dependencies:**
- [Business context document](/Context%20and%20Requirements%20Management/EN/Context/Business%20Context.md)

# Justifications
- This document covers [Innopolis University](/Context%20and%20Requirements%20Management/EN/Context/Business%20Context.md) need for risk management.

### **Risk Identification and Management Process**  
1. **Brainstorming Risks During Sprint Meetings**  
   - During each sprint meeting, the team will dedicate time to brainstorm potential risks.  
   - Risks will be evaluated based on their probability and impact, and new risks will be added to this document.  

2. **Monitoring Risks**   
   Mitigation progress will be tracked in sprint retrospectives.  

---

### **Risk Table**  

| Risk                                              | Description          | Status*                                                                                                                                                             | Probability** | Impact*** | **Proactive Countermeasures** (Preventive)                                                                 | **Retroactive Countermeasures** (Reactive)                                                                 | Assignee A | Assignee B |  
| ------------------------------------------------- | -|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------- | ------ | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------- | ---------- |  
| Permanent loss of a member                        | A member of the development team leaves the project permanently.                                                                                                             |  Mitigated   | 1           | 5      | Cross-train team members to reduce dependency on individuals.                                              | Negotiate with the customer to reduce project scope.                                                       | Yaroslav   | Kirill     |  
| Temporary loss of a member                        | A team member is unavailable for an extended period (>3 days).                                                                                                                | Mitigated  | 2           | 4      | Share plans for the week during each sprint, so that team members may step in as soon as possible.                                     | Negotiation with customer on reduction of expectations for the sprints affected or whole project.                                                              | Yaroslav   | Kirill     |  
| Denial of resources during development            | Critical resources (computational, informational, or monetary) are not delivered.                                                                                            |  Mitigated  | 3           | 4      | Document the scope and plans so that tasks can be reprioritized.                                                 | Negotiate scope reduction or seek alternative resources.                                                   | Yaroslav   | Kirill     |  
| Accidental use of restrictively licensed resource | The team unintentionally uses a non-compliant resource.                                                                                                        |        Active          | 5           | 1      | Check the requirements documentation before implementing a new resource.                                                 | Replace the resource promptly and audit for compliance.                                                    | Akam       | Vagif      |  
| Misjudgement of task laboriousness                | A task takes significantly longer than estimated, causing delays.                                                                                                         |   Mitigated   | 5           | 3      | Break tasks into smaller subtasks and validate estimates with the team.                                   | Adjust sprint goals with the customer.                                                                     | Yaroslav   | Kirill     |  
| Faulty advice from LLMs                           | The system generates incorrect guidance, leading to flawed software.                                                                                                     |   Active     | 5           | 1      | Issue warnings to stakeholders and add disclaimers to user-facing services.                                                 |  Implement popular countermeasures against LLMs inaccuracies.                               | Yaroslav   | Kirill     |  
| Faulty tests                                      | Test coverage is insufficient, leading to undetected defects.                                                                                                           |    Active     | 5           | 5      | Conduct test reviews.                                                           | Allocate additional time to improve tests and provide a remediation plan.                                  | Vagif      | Akam       |  
| Faulty process                                    | Innopolis University deems the development process non-compliant.                                                                                                      |     Mitigated     | 5           | 5      | Regularly align processes with university standards.                              | Dedicate time to process improvements and seek formal approval.                                            | Yaroslav   | Kirill     |  
| Faulty requirements                               | Elicited requirements do not match customer needs.                                                                                                                   |       Active     | 3           | 3      | Schedule frequent requirement review sessions with the customer.                                          | Clarify requirements via official communication and update documentation.                                   | Yaroslav   | Kirill     |  
| Scope creep                                       | Uncontrolled expansion of project scope without adjustments to timeline or resources.                                                                                     |  Active     | 4           | 4      | Negotiate the strict project scope with the customer.                    | Re-evaluate priorities and negotiate timeline extensions or additional resources.                           | Yaroslav   | Kirill     |  
| Security vulnerability                            | A critical security flaw is discovered in the software.                                                                                                              |     Active       | 3           | 5      | Conduct regular security audits and static code analysis.                                                 | Patch vulnerabilities and inform stakeholders promptly.                                                     | Akam       | Vagif      |  
| Third-party service outage                        | A dependent external service becomes unavailable.                                                                                                                  |        Active      | 2           | 4      | Design fallback mechanisms or alternative workflows.                                                      | Switch to backup services or implement contingency plans.                                                  | Yaroslav   | Kirill     |  

*Status: Whether the risk is: 
- Active (is a threat, but still haven't occured), 
- Mitigated (either being solved or solved completely), 
- Failed (mitigation activities did not help to reduce/avoid risk impact), 
- Irrelevant (risk is either improbable or won't affect the project).

**Chance of identified risk happening. From 1 to 5 where 1 - unlikely to happen, 5 - most likely will happen.

***How much of a project will be changed in case of encountering and mitigating this risk. From 1 to 5 where 1 - project will require a small fix, usually taking no more than 1 hour of work, 5 - whole project has to be reconsidered.

# Changelog
- v2.1 - 04.05.2025. Conversion to new format. Kirill Korikov
- v2.0 - 04.05.2025. Expanded risks. Kirill Korikov
- v1.1 - 30.03.2025.