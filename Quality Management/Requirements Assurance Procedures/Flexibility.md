# Introduction

**Version:** 1.0

**Last Edit:** 12.05.2025

**Last Editor:** Kirill Korikov

**Owner:** Yaroslav Kim

**Approval Status:** N/A

**Type:** Quality

**Description:** This document describes all the procedures associated with maintaining Flexibility.

**Dependencies:**
- [Requirements](/Context%20and%20Requirements%20Management/EN/Requirements/Software%20Product%20Requirements.md)
- [ISO 25010 Flexibility documentation](https://iso25000.com/index.php/en/iso-25000-standards/iso-25010/64-flexibility)

# Justifications
- Requirement assurance procedures must be properly documented per [Innopolis University needs](</Context and Requirements Management/EN/Context/Business Context.md>)
- Requirement assurance procedures are needed to satisfy the outlined [requirements](</Context and Requirements Management/EN/Requirements/Software Product Requirements.md>)

# Quality Requirement Assurance Plan: Flexibility(Portability)

## Quality Requirement Description
Degree to which a product can be adapted to changes in its requirements, contexts of use or system environment. This characteristic is composed of the following sub-characteristics:
- Adaptability - Degree to which a product or system can effectively and efficiently be adapted for or transferred to different hardware, software or other operational or usage environments.
- Scalability - Degree to which a product can handle growing or shrinking workloads or to adapt its capacity to handle variability.
- Installability - Degree of effectiveness and efficiency with which a product or system can be successfully installed and/or uninstalled in a specified environment.
- Replaceability - Degree to which a product can replace another specified software product for the same purpose in the same environment.

## Quality assurance/control activities
### Activity 1: Adaptability, Installability Fulfillment
**Source**: Customer's business goal defines that the system should:
- Run on machines provided by the customer.
- Include a procedure for changing the LLM used.
- Include a procedure for changing the documentation used by LLM.
 <!--What is the cause for this activity. e.g. in case of Functional Compliance this is "Customer. Customer requires a certain level of functionality to be fulfilled"-->

**Triggers**: 
- Customer will host the system on an unspecified hardware which may change in the future.
- Customer wants to test different LLMs.
- Customer may update their documentation database. <!--What happens to trigger this procedure-->

**Conductor**: Vagif Khalilov, Developer <!--Who must handle this activity (Specify a person and their qualification)-->

**Training Required:** Containerization, SOLID principles for decoupled, basic CI/CD (to implement SonarQube checking) <!--What training should the person have undertaken before activity-->

**Measurements**: Time to change the hardware/LLM/update the documentation. SonarQube circular dependencies <!--What measurements reflect the efficiency of the activity-->

**Tools**:  SonarQube (Static analysis for module cohesion), Testcontainers: Isolated testing of changed modules.  <!--What tools (software, browser extensions, etc) should be used-->

**Entry criterias**: Change in a code affects LLM or Embedding model business logic. <!--What conditions must be met to start doing the activity. For example, if we are using SonarQube to ascertain maintainability, we might forego any recommendations in regards to lets say thread safety due to some reason, so entry criteria won't be met even if a trigger for the procedure (fall in rating) fired.-->

**Effort Estimation:** Planning poker <!--What methodology could be used to estimate the amount of effort required. E.g. planning poker to estimate amount of work-hours that a developer spends-->

**Time-To-Resolution Estimation:** Adaptability issues can mostly be done during one week of one team member work, including few days of communication with the customer in cases regarding hardware discussion. <!--How to calculate amount of work-days to resolution. This is different from effort estimation because some resolutions require customer to handle some paperwork first-->

**The Procedure**: 
1. Gather updated specifications (LLM/Hardware/documentation updates).
2. Deploy the system within the updated specifications.
3. (In case of updated documentation) test the documentation upload functionality.
4. Run system with a basic input.
5. Validate system behavior (there is a response, output is consistent, all the documentation is taken into account).
<!--Describe the procedure undertaken. You may refer to other documents if necessary (for example, refer to Configuration Management if there a change in functional requirement requires a new feature to be fulfilled)-->

**Exit criterias**: 
- SonarQube score **≥A** for module independence.
- No errors during the testing.

### Activity 2: Scalability Fulfillment
**Source**: Customer's business goal defines that the system should support up to 10 concurrent users. 
 <!--What is the cause for this activity. e.g. in case of Functional Compliance this is "Customer. Customer requires a certain level of functionality to be fulfilled"-->

**Triggers**: 
Customer wants to test the system with their test group.<!--What happens to trigger this procedure-->

**Conductor**: Vagif Khalilov, Developer <!--Who must handle this activity (Specify a person and their qualification)-->

**Training Required:** Load testing, LLM quantization techniques,  <!--What training should the person have undertaken before activity-->

**Measurements**: Hardware power required to support the 10 concurrent users. <!--What measurements reflect the efficiency of the activity-->

**Tools**: Grafana  <!--What tools (software, browser extensions, etc) should be used-->

**Entry criterias**: LLM/embedding model changed, architecture changed. <!--What conditions must be met to start doing the activity. For example, if we are using SonarQube to ascertain maintainability, we might forego any recommendations in regards to lets say thread safety due to some reason, so entry criteria won't be met even if a trigger for the procedure (fall in rating) fired.-->

**Effort Estimation:** Planning poker <!--What methodology could be used to estimate the amount of effort required. E.g. planning poker to estimate amount of work-hours that a developer spends-->

**Time-To-Resolution Estimation:** The time it takes to research LLM optimization and possible architecture improvements, and implement them (may take from 1 to 2 sprints). <!--How to calculate amount of work-days to resolution. This is different from effort estimation because some resolutions require customer to handle some paperwork first-->

**The Procedure**: 
1. Make sure the system is up and running.
2. Conduct load testing using the Grafana.
3. Monitor the data and model's answers adequacy. <!--Describe the procedure undertaken. You may refer to other documents if necessary (for example, refer to Configuration Management if there a change in functional requirement requires a new feature to be fulfilled)-->

**Exit criterias**: All 10 users complete tasks without errors. Response times don't deviate under the tested load. <!--What conditions must be met to stop doing the activity-->


### Activity 3: Replaceability Fulfillment
**Source**: Customer's business goal defines that the system must be able to connect with any of their resources (webpages, front-end clients, etc.). 
 <!--What is the cause for this activity. e.g. in case of Functional Compliance this is "Customer. Customer requires a certain level of functionality to be fulfilled"-->

**Triggers**: 
Customer wants to send a request to the system from a new resource..<!--What happens to trigger this procedure-->

**Conductor**: Vagif Khalilov, Developer <!--Who must handle this activity (Specify a person and their qualification)-->

**Training Required:** Basics of networking, architectural design <!--What training should the person have undertaken before activity-->

**Measurements**: Time it takes to adapt to the system's API from a new resource. <!--What measurements reflect the efficiency of the activity-->

**Tools**: Swagger <!--What tools (software, browser extensions, etc) should be used-->

**Entry criterias**: API layer of the system changed <!--What conditions must be met to start doing the activity. For example, if we are using SonarQube to ascertain maintainability, we might forego any recommendations in regards to lets say thread safety due to some reason, so entry criteria won't be met even if a trigger for the procedure (fall in rating) fired.-->

**Effort Estimation:** Planning poker <!--What methodology could be used to estimate the amount of effort required. E.g. planning poker to estimate amount of work-hours that a developer spends-->

**Time-To-Resolution Estimation** Must take into account Internet connection issues and access to the client's hardware. <!--How to calculate amount of work-days to resolution. This is different from effort estimation because some resolutions require customer to handle some paperwork first-->

**The Procedure**: 
1. Make sure that all the required functionality is accessible via Swagger page.
2. Run through the Swagger endpoints to make sure that the system responds consistently.

**Exit criterias**: Swagger page is up and running. All the requested functionality is available via the system API. All the responses are consistent. <!--What conditions must be met to stop doing the activity-->


# Changelog
- v1.0 12/05/2025 - Initial version by Kirill Korikov.
