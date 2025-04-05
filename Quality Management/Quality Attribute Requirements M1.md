# Functional Requirements

**Note on actors**: users do not interact with the system directly, but via a third-party solution. Developers or administrators will interact with the system directly when building the user-facing product.

**Note on terminology**: we use words "System", "The product", and "Chatbot" interchangeably - all of them mean the product that we are producing.

**Note on definitions**: definitions of quality attributes and their sub-attributes are taken from [ISO 25010](https://iso25000.com/index.php/en/iso-25000-standards/iso-25010)

### User Stories

1. As a **developer**, I want to submit queries via an API endpoint so that I can receive answers in Russian with direct links to relevant documentation sections.
2. As a **developer**, I want the system to only use approved AuroraOS and GitLab sources for answers so that responses are accurate and avoid irrelevant information.
3. As a **user**, I want responses formatted in Markdown and written in Russian so that I can easily read and use the answers.
4. As a **user**, I want response to my question take no longer than 2 minutes from the moment it starts being processed.

---

### Use Cases

**Use Case: Retrieve Documentation Answer**

**Actor**: Developer/User

**Preconditions**: User/Developer has valid access to the API endpoint.

**Flow**:

1. User sends a request to the API endpoint with a question about AuroraOS documentation.
2. The system validates the request and searches the approved documentation sources (AuroraOS sections, GitLab demos/examples).
3. The system constructs a response using only information from the approved sources, excludes unrelated content, and formats the answer in Markdown.
4. The system ensures the response is in Russian and includes direct links to the referenced documentation pages.
5. The response is returned to the user.**Postconditions**: User receives a structured, sourced answer in Russian.

**Use Case: Inform of Inability to Answer**

**Actor**: Developer/User

**Preconditions**: User/Developer has valid access to the API endpoint.

**Flow**:

1. User sends a request to the API endpoint with a question about AuroraOS documentation, that is not answered in the existing documentation.
2. The system validates the request and searches the approved documentation sources (AuroraOS sections, GitLab demos/examples).
3. The system correctly identifies that it does not have any relevant information available and provides a response that explains inability to answer the question
4. The system ensures the response is in Russian.
5. The response is returned to the user.**Postconditions**: User receives an answer that communicates non-existence of answer to their question within the documentation.

---

### Features

1. **API Query Processing**
    - Accept user queries via a dedicated API endpoint (e.g., `POST /api/request).
2. **Markdown Response Generation**
    - Format answers in Markdown.
3. **Russian Language Enforcement**
    - All responses are generated exclusively in Russian.
4. **Link Inclusion**
    - Embed direct links to source documentation pages (e.g., `[AuroraOS Guide](<https://developer.auroraos.ru/doc/5.1.1/software_development/guides/example.md>)`).
5. *Prevent Hallucinations
    - Answers are derived only from:
        - AuroraOS `/guides` and `/extended` sections (v5.1.1).
        - GitLab `demos` and `examples` repositories.**
    - Do not provide answers to questions that provided documentation and examples cannot answer.
    - Only provide answers relevant to AuroraOS.
---

### Interfaces

### API Endpoint Specification

Note: endpoint specifications are tentative. May change in the future

- **Endpoint**: `/api/query`
- **Method**: `POST`
- **Request Body**:
    
    ```json
    {
      "query": "Как настроить AuroraOS SDK?",
    }
    ```
    
- **Response Body** (Success):

```markdown
  ### Ответ:
  Для настройки AuroraOS SDK выполните следующие шаги:
  1. Установите базовые зависимости через [Aurora Store](<https://developer.auroraos.ru/doc/5.1.1/software_development/guides/setup.md>).
  2. Настройте среду разработки, как описано в [примерах GitLab](<https://gitlab.com/omprussia/examples/env-config>).

```

- **Error Handling**:
    - Returns `400 Bad Request` if `query` is empty.

---

### Design Constraints

- The system should not use external APIs such as OpenAI during its work.
- The system should only use software/libraries/packages/resources that allow commercial use and distribution
Here’s the document with formatting inconsistencies resolved while preserving all content:

---
<!-- REMOVED due to recitation instruction 2
# Functional Suitability

Per ISO 25010 - Functional Suitability is the degree to which a product fulfills stated and implied functions under specified conditions.

---

## Functional Completeness

Degree to which the set of functions covers all the specified tasks and intended users' objectives.

1. **Source**: Developer/User submitting a query via the API.
2. **Stimulus**: A query requiring accurate answers derived from documentation is received.
3. **Environment**: The system is operational, with access to the documentation repositories.
4. **Artifact(s)**: API endpoint, approved documentation sources.
5. **Response**: A Markdown response in Russian with hyperlinks to relevant documentation.
6. **Response Measure**:
    - Complete coverage of the specified functions (API integration, Markdown formatting, Russian language, link inclusion, and hallucination prevention).

---

## Functional Correctness

Degree to which a product or system provides accurate results when used by intended users.

1. **Source**: Developer/User submitting a query via the API.
2. **Stimulus**: A query requiring accurate answers derived from documentation is received.
3. **Environment**: The system is operational, with access to the documentation repositories.
4. **Artifact(s)**: Query content, documentation sources.
5. **Response**:
    - An answer containing *only* information from approved sources, with no hallucinations or external references.
    - An answer that explains that existing documentation is insufficient to answer the question if that is the case.
6. **Response Measure**:
    - For 90% of answers, at least 90% of users in the testing group identify the answer as correct, helpful, and relevant.
    - For 90% of answers, at least 90% of users in the testing group identify the answer as correct if the system communicated that the answer cannot be produced using existing documentation.

---

## Functional Appropriateness

Degree to which the functions facilitate the accomplishment of specified tasks and objectives.

1. **Source**: Developer/User submitting a query via the API.
2. **Stimulus**: A query requiring accurate answers derived from documentation is received.
3. **Environment**: The system is operational, with access to the documentation repositories.
4. **Artifact(s)**: API response in Markdown format.
5. **Response**: A concise, actionable answer formatted for readability and further use.
6. **Response Measure**:
    - For 90% of answers, at least 90% of users in the testing group report reduced time spent searching documentation in comparison to existing solution (Yandex indexed search).

**Note**: The testing group will be provided by the customer. Later, the metrics may change and cover a bigger set of users.

---
-->

# Performance Efficiency

Degree to which a product performs its functions within specified time and throughput parameters and is efficient in the use of resources under specified conditions

---

## Time Behaviour

The response time and throughput rates of a product.

1. **Source**: User.
2. **Stimulus**: User sends a message.
3. **Environment**: Normal operation. Hardware hosting the product meets specified requirements.
4. **Artifact(s)**: Chatbot.
5. **Response**: Return an answer within a specified time.
6. **Response Measure**: Difference between logged times of accepting the message from the API and sending the response back to the API should not exceed **2 minutes**.

**Note**: This measure was discussed with the customer and confirmed as appropriate.

---

## Resource Utilization

The amounts and types of resources used by a product.

1. **Source**: Chatbot.
2. **Stimulus**: Chatbot generates a response.
3. **Environment**: Normal operation with no more than 10 concurrent users.
4. **Artifact(s)**: Hardware that hosts the chatbot.
5. **Response**: Use minimum required resources to generate a response.
6. **Response Measure**: The hardware utilizes no more than **12 GB of RAM**.

A common formula to estimate GPU memory for serving an LLM:

`M = (32/Q)(P * 4B) * 1.2`, where:

| **M** | GPU memory (GB) |
| --- | --- |
| **P** | Model parameters (e.g., 0.5B = 500,000,000) |
| **Q** | Bits for loading the model (e.g., 16 bits) |
| **1.2** | 20% overhead for additional GPU memory usage. |

**Calculation**:

`(500,000,000 * 4B) / (32/16) * 1.2 = 12 GB`.

---

## Capacity

The maximum limits of a product.

1. **Source**: API.
2. **Stimulus**: Number of concurrent users exceeds one.
3. **Environment**: Normal operation. Hardware hosting the product meets specified requirements.
4. **Artifact(s)**: Chatbot.
5. **Response**: Chatbot performs with no observable degradation.
6. **Response Measure**: The system shall support **concurrent usage by up to 10 active users** without degradation of response time or accuracy.

**Note**: This measure was provided by customer requirements.

---

# Compatibility

Degree to which a product, system, or component can exchange information with other products, systems, or components, and/or perform its required functions while sharing the same common environment and resources.

---

## Co-Existence

Degree to which a product can perform its required functions efficiently while sharing a common environment and resources with other products, without detrimental impact on any other product.
**Non-Applicable**

**Justification**: Our system doesn’t interact with external systems that necessitate co-existence considerations.

---

## Interoperability

Degree to which a system, product, or component can exchange information with other products and mutually use the information exchanged.

1. **Source**: External system.
2. **Stimulus**: API calls from an external system.
3. **Environment**: Production environment.
4. **Artifact**: API interface.
5. **Response**: Successful communication with the external system.
6. **Response Measure**: 100% compatibility with standard HTTP clients.

---

# Usability

Degree to which a product or system can be interacted with by specified users to exchange information via the user interface to complete specific tasks in a variety of contexts of use.

---

## Appropriateness Recognizability

Degree to which users can recognize whether a product or system is appropriate for their needs.
**Non-Applicable**

**Justification**: No user interfaces (UI/UX) are provided beyond the API.

---

## Learnability

Degree to which the functions of a product or system can be learnt to be used by specified users within a specified amount of time
**Non-Applicable**

**Justification**: No user interfaces are provided.

---

## Operability

Degree to which a product or system has attributes that make it easy to operate and control.
**Non-Applicable**

**Justification**: No user interfaces are provided.

---

## User Error Protection

Degree to which a system prevents users against operation errors.
**Non-Applicable**

**Justification**: No user interfaces are provided.

---

## User Interface Aesthetics

Degree to which a user interface presents functions and information in an inviting and motivating manner encouraging continued interaction.
**Non-Applicable**

**Justification**: No user interfaces are provided.

---

## Accessibility

Degree to which a product or system can be used by people of various backgrounds (such as people of various ages, abilities, cultures, ethnicities, languages, genders, economic situations, etc.).
**Non-Applicable**

**Justification**: No user interfaces are provided.

---

# Reliability

Degree to which a system, product, or component performs specified functions under specified conditions for a specified period of time.

---

## Faultlessness

Degree to which a system, product or component performs specified functions without fault under normal operation.

1. **Source**: System operation.
2. **Stimulus**: Ongoing use over time.
3. **Environment**: Production environment.
4. **Artifact(s)**: Complete system.
5. **Response**: Stable operation.
6. **Response Measure**: Rate of critical incidents < 1% after 3 months of operation.

---

## Availability

Degree to which a system, product or component is operational and accessible when required for use.

1. **Source**: Users.
2. **Stimulus**: System access attempts.
3. **Environment**: Production environment.
4. **Artifact(s)**: Complete system.
5. **Response**: System is operational.
6. **Response Measure**: 99.9% uptime.

---

## Fault Tolerance

Degree to which a system, product or component operates as intended despite the presence of hardware or software faults.

1. **Source**: System components.
2. **Stimulus**: Component failure.
3. **Environment**: Production environment.
4. **Artifact(s)**: System architecture.
5. **Response**: Continued operation despite failures.
6. **Response Measure**: No complete service interruption when non-critical components fail.

---

## Recoverability

Degree to which, in the event of an interruption or a failure, a product or system can recover the data directly affected and re-establish the desired state of the system.

1. **Source**: System failure.
2. **Stimulus**: Critical error or crash.
3. **Environment**: Production environment.
4. **Artifact(s)**: Recovery systems.
5. **Response**: System returns to operational state.
6. **Response Measure**: Recovery < 1 hour with no data loss.

---

# Security

Degree to which a product or system defends against attack patterns by malicious actors and protects information and data.

---

## Confidentiality

Degree to which a product or system ensures that data are accessible only to those authorized to have access.
**Non-Applicable**

**Justification**: The system processes only publicly available documentation.

---

## Integrity

Degree to which a system, product or component ensures that the state of its system and data are protected from unauthorized modification or deletion either by malicious action or computer error.

1. **Source**: Users.
2. **Stimulus**: Submission of a documentation query.
3. **Environment**: Production environment.
4. **Artifact(s)**: API, LLM Controller, Database.
5. **Response**: Data provided in responses is unaltered and sourced from approved documentation.
6. **Response Measure**: Rate of inaccurate responses reported by users is below a predefined threshold.

---

## Non-Repudiation

Degree to which actions or events can be proven to have taken place so that the events or actions cannot be repudiated later.
**Non-Applicable**

**Justification**: No requirement to track query origins for legal purposes.

---

## Accountability

Degree to which the actions of an entity can be traced uniquely to the entity.
**Non-Applicable**

**Justification**: Detailed user action tracking is not required.

---

## Authenticity

Degree to which the identity of a subject or resource can be proved to be the one claimed.
**Non-Applicable**

**Justification**: No user authentication is required.

---

# Portability

Degree to which a product can be adapted to changes in its requirements, contexts of use or sys tem environment. This characteristic is composed of the following sub-characteristics:

---

## Adaptability

Degree to which a product or system can effectively and efficiently be adapted for or transferred to different hardware, software or other operational or usage environments.
**Non-Applicable**

**Justification**: The system is designed for a specific environment (to be specified by the customer).

---

## Installability

Degree to which a product can handle growing or shrinking workloads or to adapt its capacity to handle variability.

1. **Source**: System administrators.
2. **Stimulus**: System installation.
3. **Environment**: Server environment.
4. **Artifact(s)**: Package and dependency installation.
5. **Response**: Successful installation.
6. **Response Measure**: Complete installation within 1 hour following documentation.

---

## Replaceability

Degree to which a product can replace another specified software product for the same purpose in the same environment.

1. **Source**: System administrators.
2. **Stimulus**: Decision to upgrade/change the LLM model.
3. **Environment**: Production environment.
4. **Artifact(s)**: LLM Controller.
5. **Response**: System updated to use the new LLM model with minimal disruption.
6. **Response Measure**:
    - LLM model switched in < 2 hours with a rollback strategy.
    - No changes required to other components.
    - Functionality and accuracy maintained post-switch.
    - Automated tests pass after replacement.

---

# Maintainability

Degree of effectiveness and efficiency with which a product or system can be modified

---

## Modularity

Degree to which a system or computer program is composed of discrete components such that a change to one component has minimal impact on other components.
**Applicable**

1. **Source**: Developer team.
2. **Stimulus**: Request for a new feature, bug fix, or change.
3. **Environment**: Development environment, code repository (e.g., Git).
4. **Artifact(s)**: Source code (requests processing, LLM interactions, documentation access).
5. **Response**: Code modifications in one module do not affect others.
6. **Response Measure**: Time to implement changes, Cyclomatic Complexity, number of affected modules.

---

## Reusability

Degree to which a product can be used as an asset in more than one system, or in building other assets.
**Applicable**

1. **Source**: Development team, other projects.
2. **Stimulus**: Need for similar functionality in another project.
3. **Environment**: Project repository, shared library repository.
4. **Artifact(s)**: Documentation access, LLM, API request handler modules.
5. **Response**: Modules can be extracted and reused.
6. **Response Measure**: Time to integrate into other projects, dependency count, documentation quality.

---

## Analysability

Degree of effectiveness and efficiency with which it is possible to assess the impact on a product or system of an intended change to one or more of its parts, to diagnose a product for deficiencies or causes of failures, or to identify parts to be modified.
**Applicable**

1. **Source**: Developer team.
2. **Stimulus**: Requirement to debug or assess code impact.
3. **Environment**: Development environment, code repository.
4. **Artifact(s)**: Source code, comments, documentation.
5. **Response**: Code base is easy to understand.
6. **Response Measure**: Time to understand modules, code smells detected, code comment coverage.

---

## Modifiability

Degree to which a product or system can be effectively and efficiently modified without introducing defects or degrading existing product quality
**Applicable**

1. **Source**: Developer team, customer.
2. **Stimulus**: Change request or bug report.
3. **Environment**: Development environment.
4. **Artifact(s)**: Source code, configuration files.
5. **Response**: Changes implemented with minimal disruption.
6. **Response Measure**: Time to implement, lines of code changed, bugs introduced.

---

## Testability

Degree of effectiveness and efficiency with which test criteria can be established for a system, product or component and tests can be performed to determine whether those criteria have been met.
**Applicable**

1. **Source**: Developer team, testing framework.
2. **Stimulus**: Requirement to verify correctness.
3. **Environment**: Testing environment, CI/CD pipeline.
4. **Artifact(s)**: Source code, test cases, test data.
5. **Response**: Application can be easily tested.
6. **Response Measure**: Code coverage %, number of test cases, test runtime, use of mocking.

# Prioritization of Quality Requirements

We can outline four main quality requirements that we wish to focus on in the following priority (highest to lowest):

1. Performance - the goal of the project is to make using the documentation faster, hence the product should produce answers fast enough to be a better choice than making a Yandex-indexed search
2. Maintainability - the product will later on be handed off to the customer, who will want to modify it and deploy it themselves, and it also needs to be easy to maintain throughout half a year of development. Hence, it is important to keep the product as maintainable as possible.
3. Portability - the product should be easy to install and it should be easy to replace its parts and products it uses.
4. Reliability - the product should be reliable enough to not stop working at random.