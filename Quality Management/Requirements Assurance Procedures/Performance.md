# Introduction

**Version:** 1.0

**Last Edit:** 12.05.2025

**Last Editor:** Akam Temitope

**Owner:** Yaroslav Kim

**Approval Status:** N/A

**Type:** Process

**Description:** This document describes all the procedures associated with maintaining Performance

**Dependencies:**

- [Requirements](/Context%20and%20Requirements%20Management/EN/Requirements/Software%20Product%20Requirements.md)
- [Business Context](/Context%20and%20Requirements%20Management/EN/Context/Business%20Context.md)

# Justifications

- Requirement assurance procedures must be properly documented per [Innopolis University needs](</Context and Requirements Management/EN/Context/Business Context.md>)
- Requirement assurance procedures are needed to satisfy the outlined [requirements](</Context and Requirements Management/EN/Requirements/Software Product Requirements.md>)

# Quality Requirement Assurance Plan: Performance

## Quality Requirement Description

This characteristic represents the degree to which a product performs its functions within specified time and throughput parameters and is efficient in the use of resources (such as CPU, memory, storage, network devices, energy, materials...) under specified conditions.

## Quality assurance/control activities

### Activity 1: Time Behaviour Fulfillment

**Source**: **Requirement 2.1.1**: "The system shall provide responses to queries within ≤2 minutes under the following conditions."<!--What is the cause for this activity. e.g. in case of Functional Compliance this is "Customer. Customer requires a certain level of functionality to be fulfilled"-->

**Triggers**:

- Implementation or modification of LLM model or retrieval logic.
- Deployment on new infrastructure or GPU.
- Reported complaint or detected regression in performance metrics.
<!--What happens to trigger this procedure-->

**Conductor**: Akam Temitope, Developer<!--Who must handle this activity (Specify a person and their qualification)-->

**Training Required:**

- Understanding LLM inference latency
- API monitoring and instrumentation
  general familiarity with LLM Quantization<!--What training should the person have undertaken before activity-->

**Measurements**:

- **P95 Latency** = 95th percentile of response time across real queries. Target: of ≤ 2 minutes
- **Cold Start vs. Warm Response Time** - First response after container/LLM startup vs. subsequent average
- **Average Response Time** under max concurrency (10 users)
- **System Throughput** = Number of queries successfully processed per minute under load
<!--What measurements reflect the efficiency of the activity-->

**Tools**:

- **Prometheus** - metrics collection
- **Grafana** - performance dashboard visualization
- **Locust** - load testing up to 10 concurrent users
<!--What tools (software, browser extensions, etc) should be used-->

**Entry criteria**:

- The system is deployed and accessible via its public API.
- The LLM is running on target hardware (GPU or CPU).
- Retrieval and formatting components are functional and integrated.
- LLM quantization and prompt parameters are finalized and not expected to change during the test.
<!--What conditions must be met to start doing the activity. For example, if we are using SonarQube to ascertain maintainability, we might forego any recommendations in regards to lets say thread safety due to some reason, so entry criteria won't be met even if a trigger for the procedure (fall in rating) fired.-->

**Effort Estimation:** 4 story points <!--What methodology could be used to estimate the amount of effort required. E.g. planning poker to estimate amount of work-hours that a developer spends-->

**Time-To-Resolution Estimation:** Estimated by conductor/manager <!--How to calculate amount of work-days to resolution. This is different from effort estimation because some resolutions require customer to handle some paperwork first-->

**The Procedure**:

- Set up monitoring stack (Prometheus, Grafana) and load testing infrastructure.
- Define representative query batches
- Run baseline performance test at 1 user, then scale to 10 concurrent users.
- Record and visualize response times (avg, P95).
- Investigate slow queries using logs and GPU/CPU metrics.
- Generate final performance report
<!--Describe the procedure undertaken. You may refer to other documents if necessary (for example, refer to Configuration Management if there a change in functional requirement requires a new feature to be fulfilled)-->

**Artifacts**:

- Performance Test Plan
- Grafana Dashboards (Snapshot exports)
- Response Time Logs (JSON/CSV)
- Final Report

\*_Exit criteria_:

- P95 Latency ≤ 2 minutes for full query batch
- System supports 10 concurrent users with no increased average latency
<!--What conditions must be met to stop doing the activity-->

# Changelog

- v1.4 12/05/2025 - update by Akam Temitope
- v1.3 13/04/2025 - conversion of document to current format by Yaroslav Kim
