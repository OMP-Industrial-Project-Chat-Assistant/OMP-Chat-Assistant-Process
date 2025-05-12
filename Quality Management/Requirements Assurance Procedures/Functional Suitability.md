# Introduction

**Version:** 1.0

**Last Edit:** 12.05.2025

**Last Editor:** Akam Temitope

**Owner:** Yaroslav Kim

**Approval Status:** N/A

**Type:** Process

**Description:** This document describes all the procedures associated with maintaining Functional Suitability

**Dependencies:**

- [Requirements](/Context%20and%20Requirements%20Management/EN/Requirements/Software%20Product%20Requirements.md)
- [Business Context](/Context%20and%20Requirements%20Management/EN/Context/Business%20Context.md)

# Justifications

- Requirement assurance procedures must be properly documented per [Innopolis University needs](</Context and Requirements Management/EN/Context/Business Context.md>)
- Requirement assurance procedures are needed to satisfy the outlined [requirements](</Context and Requirements Management/EN/Requirements/Software Product Requirements.md>)

# Quality Requirement Assurance Plan: Functional Suitability

## Quality Requirement Description

This characteristic represents the degree to which a product or system provides functions that meet stated and implied needs when used under specified conditions.

## Quality assurance/control activities

### Activity 1: Functional Correctness Fulfillment

**Source**: Requirement 1.1.1–1.1.6 specifying essential API capabilities. <!--What is the cause for this activity. e.g. in case of Functional Compliance this is "Customer. Customer requires a certain level of functionality to be fulfilled"-->

**Triggers**: Completion of implementation of all API-related functionalities.<!--What happens to trigger this procedure-->

**Conductor**: Yaroslav Kim, Manager

<!--Who must handle this activity (Specify a person and their qualification)-->

**Training Required:**

- Understanding of requirement traceability.
- Familiarity with the defined endpoints and expected behaviors
- Russian language understanding to validate responses.
<!--What training should the person have undertaken before activity-->

**Measurements**:

- **Coverage Score** = (# of requirements with verified implementation / 6 total defined API requirements) × 100%
- **Customer Approval** = % of test cases confirmed as "acceptable" by customer
<!--What measurements reflect the efficiency of the activity-->

**Tools**:

- **Requirement Test Matrix** (e.g. Excel) – Maps requirements to test cases.
- **Postman** – For testing each API endpoint.
- **GitHub Issues** – Tracks uncovered or failed functionalities.<!--What tools (software, browser extensions, etc) should be used-->

**Entry criteria**:

- All defined functional requirements (1.1.1–1.1.6) implemented.
- Internal endpoint documentation is available for testing.
<!--What conditions must be met to start doing the activity. For example, if we are using SonarQube to ascertain maintainability, we might forego any recommendations in regards to lets say thread safety due to some reason, so entry criteria won't be met even if a trigger for the procedure (fall in rating) fired.-->

**Effort Estimation:** 5 story points <!--What methodology could be used to estimate the amount of effort required. E.g. planning poker to estimate amount of work-hours that a developer spends-->

**Time-To-Resolution Estimation:** Estimated by conductor/manager <!--How to calculate amount of work-days to resolution. This is different from effort estimation because some resolutions require customer to handle some paperwork first-->

**The Procedure**:

- Review functional requirements and map each to at least one test case.
- Execute all test cases using Postman.
- Record results in the requirement test matrix.
- Demo validated output to customer.
- Collect customer feedback in Telegram or review sheet.
- Fix and retest if any requirement fails or is not acknowledged.
<!--Describe the procedure undertaken. You may refer to other documents if necessary (for example, refer to Configuration Management if there a change in functional requirement requires a new feature to be fulfilled)-->

**Artifacts**:

- Requirement Test Matrix (input/output)
- Customer feedback
- QA logs of test results

**Exit criteria**:

- 100% of functional requirements tested and verified.
- At least 95% approved by customer
- All flagged issues resolved.
<!--What conditions must be met to stop doing the activity-->

### Activity 2: Functional Correctness Fulfillment

**Source**: Requirements 1.1.3–1.1.5 which focus on correctness of responses.

<!--What is the cause for this activity. e.g. in case of Functional Compliance this is "Customer. Customer requires a certain level of functionality to be fulfilled"-->

**Triggers**: Each time the data sources are changed/updated, or hallucination issues are suspected. <!--What happens to trigger this procedure-->

**Conductor**: Yaroslav Kim, Manager

<!--Who must handle this activity (Specify a person and their qualification)-->

**Training Required:**

- Russian fluency to validate linguistic correctness.
- Awareness of documentation source scope.
- Ability to identify hallucinated LLM content.
<!--What training should the person have undertaken before activity-->

**Measurements**:

- **Correctness Accuracy** = (# of responses matching expected answers / total tested prompts) × 100%
- **Source Error Rate**= (# of responses using unapproved content ÷ total responses) × 100%
- **Language Accuracy** = (# of responses fully in Russian / total responses) × 100%
<!--What measurements reflect the efficiency of the activity-->

**Tools**:

- **QA prompt suite**: Standardized questions that test correctness.
<!--What tools (software, browser extensions, etc) should be used-->

**Entry criteria**: API endpoint returns results to prompt suite.

<!--What conditions must be met to start doing the activity. For example, if we are using SonarQube to ascertain maintainability, we might forego any recommendations in regards to lets say thread safety due to some reason, so entry criteria won't be met even if a trigger for the procedure (fall in rating) fired.-->

**Effort Estimation:** 5 story points <!--What methodology could be used to estimate the amount of effort required. E.g. planning poker to estimate amount of work-hours that a developer spends-->

**Time-To-Resolution Estimation:** Estimated by conductor/manager <!--How to calculate amount of work-days to resolution. This is different from effort estimation because some resolutions require customer to handle some paperwork first-->

**The Procedure**:

- Define QA prompt set covering common and edge-case queries.
- Run each prompt through the API.
- For each response:
  - Check that the result answers the question accurately.
  - Ensure only allowed source data is referenced.
  - Confirm the language is Russian.
- Document results in correctness matrix.
- Log any incorrect results and notify dev team.
- Re-run test set after fix and record outcome.
<!--Describe the procedure undertaken. You may refer to other documents if necessary (for example, refer to Configuration Management if there a change in functional requirement requires a new feature to be fulfilled)-->

**Artifacts**

- QA Prompt List
- Correctness Matrix

**Exit criteria**:

- ≥ 90% correctness
- 0% external source usage
- 100% Russian language compliance
<!--What conditions must be met to stop doing the activity-->

# Changelog

- v1.4 12/05/2025 - update by Akam Temitope
- v1.3 13/04/2025 - conversion of document to current format by Yaroslav Kim
