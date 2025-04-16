# Introduction

**Version:** 1.4

**Last Edit:** 16/04/2025

**Last Editor:** Yaroslav Kim

**Owner:** Yaroslav Kim

**Approval Status:** N/A

**Type:** Requirements

**Description:** This document is a list of functional and quality requirements to the project.

**Dependencies:**
 - [Generic Document Template](<../../../DocumentTemplates/EN/Generic Document Template.md>)
 - [Политика Требований](<../../RU/Требования/Политика Требований.md>)
 - [Требования к Продукту](<../../RU/Требования/Требования к Продукту.md>)

# Justifications
This document exists to provide concrete requirements to measure project's completion.

# Content

Русская версия: [Требования к Продукту](<../../RU/Требования/Требования к Продукту.md>)


## 1. Functional Requirements  

### 1.1 API Integration & Response Handling  
The system shall:  
1.1.1 Process user queries related to documentation via a defined API endpoint.  
1.1.2 Return responses in Markdown format containing detailed answers to the submitted queries.  
1.1.3 Generate responses **exclusively in Russian**.  
1.1.4 Construct answers using **only** the following documentation sources:  
- Source files from the AuroraOS section: [`https://developer.auroraos.ru/doc/5.1.1/software_development/guides`](https://developer.auroraos.ru/doc/5.1.1/software_development/guides) (Markdown format)  
- Source files from the AuroraOS section: [`https://developer.auroraos.ru/doc/5.1.1/extended`](https://developer.auroraos.ru/doc/5.1.1/extended) (Markdown format)  
- Files from the GitLab repository: [`https://gitlab.com/omprussia/demos`](https://gitlab.com/omprussia/demos)  
- Files from the GitLab repository: [`https://gitlab.com/omprussia/examples`](https://gitlab.com/omprussia/examples) 
- Documentation on additional tools
1.1.5 Exclude any information unrelated to the provided documentation sources.  
1.1.6 Include direct hyperlinks to the referenced documentation pages within responses.  

---

## 2. Non-Functional Requirements  
The team follows ISO25010 quality model. The following are quality attributes and sub-attributes, for which specific, measurable, and actionable procedures have been established.
### 2.1 Performance
2.1.1 **Time behaviour**: The system shall provide responses to queries within **≤2 minutes** under the following conditions
2.1.2 **Resource Utilization**: The system should not utilize more than `M` GB of GPU memory. M is a value dependent on the chosen LLM parameters.
`M = (32/Q)(P * 4B) * 1.2`, where:

| **M**   | GPU memory (GB)                               |
| ------- | --------------------------------------------- |
| **P**   | Model parameters (e.g., 0.5B = 500,000,000)   |
| **Q**   | Bits for loading the model (e.g., 16 bits)    |
| **1.2** | 20% overhead for additional GPU memory usage. |
`(500,000,000 * 4B) / (32/16) * 1.2 = 12 GB`.
2.1.3 **Capacity**: The system shall support **concurrent usage by up to 10 active users** without degradation of response time or accuracy.

### 2.2 Maintainability  
2.2.1 **Modularity**: Whenever a specific module's behavior needs to be altered, only it and its submodules are affected.
2.2.2 **Analysability**: The product shall include **comprehensive documentation in Russian** covering:  
- Deployment procedures and infrastructure requirements.  
- User guide for interacting with the API.  
- Instructions for modifying or adding content sources used for response generation.
- Instructions on product internal works
- Versioning strategy for:  
	- The product’s own documentation (e.g., release notes, changelogs).  
    - External documentation sources (e.g., AuroraOS, GitLab repos).
2.2.3 **Testability**: The product shall include mechanisms for testing the LLM efficiency, database efficiency, and central server efficiency. Every module should be structured in a way that allows mock testing.

### 2.3 Flexibility
2.3.1 **Adaptability**: The system should:
- Run on machines provided by the customer
- Include a procedure for changing the LLM used
- Include a procedure for changing the documentation used by LLM
2.3.2 **Scalability**: The system should provide balancing of load between up to 10 users
2.3.3 **Installability**: The system should include a procedure for installation that succeeds in expected environments
2.3.4 **Replaceability**: The system should communicate with other systems via a singular API

## 3. Constraints  

### 3.1 Third-Party Dependencies  
3.1.1 The system **shall not** utilize external APIs, services, or resources during operation.  

### 3.2 Licensing  
3.2.1 All software components, libraries, and dependencies must be licensed under terms permitting **commercial use by Aurora OS** without restrictions.  

# Changelog
- v1.4. 16/04/2025 Yaroslav Kim. Link fixes
- v1.3. 13/04/2025 Kirill Korikov updated the document to the new template.
- v1.2 16/03/2025 Yaroslav Kim. Expansion of document and alignment with ISO 25010
- v1.1 10/03/2025 Yaroslav Kim. Clarifications on documentation coverage requirements from Mr. Suvorov.
- v1.0 21/02/2025 Yaroslav Kim. Initial release.