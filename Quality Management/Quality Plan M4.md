# Quality Assurance Activities

## Functional Suitability

### Quality Requirement Description

This characteristic represents the degree to which a product or system provides functions that meet stated and implied needs when used under specified conditions.

### Quality assurance/control activities

#### Activity 1: Functional Correctness Fulfillment

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

#### Activity 2: Functional Correctness Fulfillment

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

## Performance

### Quality Requirement Description

This characteristic represents the degree to which a product performs its functions within specified time and throughput parameters and is efficient in the use of resources (such as CPU, memory, storage, network devices, energy, materials...) under specified conditions.

### Quality assurance/control activities

#### Activity 1: Time Behaviour Fulfillment

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

## Maintainability
### Quality Requirement Description

This characteristic represents the degree of effectiveness and efficiency with which a product or system can be modified to improve it, correct it or adapt it to changes in environment, and in requirements.

---

### Quality Requirement Assurance Plan: Maintainability  
*Aligned with ISO25010 and Business Constraints*

---

#### **Activity 1: Architectural Modularity Assurance**  
**Source:** Ensure ease of product development
**Triggers:**  
- Report of cascading failures after a module change  
- Aurora OS documentation version update requiring integration  

##### **Training Required**  
1. **SOLID Principles**: To enforce decoupled, single-responsibility modules.
2. **Chaos Testing**: To validate failure isolation (critical for GPU-bound systems).  

##### **Measurements**  
| Metric | Target | Measurement Method |  
|--------|--------|--------------------|  
| Cross-module failure rate | 0% | Automated integration tests post-change |  
| Dependency depth | ≤2 layers | SonarQube dependency analysis |  
| Interface stability | ≥90% unchanged APIs | API spec version diff |  

##### **Tools**  
1. **Draw.io**: Collaborative diagramming to visualize/modify architecture (supports real-time team edits).  
2. **SonarQube**: Static analysis for circular dependencies/module coupling.  
3. **Testcontainers**: Isolated testing of module interactions.  

##### **Entry Criteria**  
- Incident tracker reports **≥2 unrelated component failures** caused by a single module change.  
- SonarQube flags **>3 circular dependencies** in a module.  

##### **Effort Estimation**  
- Minor refactor: **3 story points** 
- Major redesign: **12 story points**   

##### **Time-to-Resolution**  
- Estimated by lead developer based on sprint capacity.  

##### **Procedure**  
1. **Triage**:  
   - Assign issue in github with description.    
2. **Analysis**:  
   - Run `sonar-scanner --dependency-check`.  
   - Generate dependency graph via `draw.io`.  
3. **Redesign**:  
   - Define new interfaces.  
   - Conduct peer review with another developer.  
4. **Testing**:  
   - Deploy to `test` environment with chaos monkey (random module failures).  
   - Validate isolation via `pytest -m "integration"`.  
5. **Documentation**:  
   - Update `Architectural Design/Architecture.md` with revised diagrams.    

##### **Artifacts**  
- **Input**: Incident report, SonarQube analysis  
- **Output**: Updates contracts between modules, Chaos test results, Update diagrams in `Architectural Management` folder  

##### **Exit Criteria**  
- **Zero** cross-module failures in 72 hours of chaos testing.
- SonarQube score **≥A** for module independence.
- Approval by 3/4 developers.

---

## Flexibility
### Quality Requirement Description
Degree to which a product can be adapted to changes in its requirements, contexts of use or system environment. This characteristic is composed of the following sub-characteristics:
- Adaptability - Degree to which a product or system can effectively and efficiently be adapted for or transferred to different hardware, software or other operational or usage environments.
- Scalability - Degree to which a product can handle growing or shrinking workloads or to adapt its capacity to handle variability.
- Installability - Degree of effectiveness and efficiency with which a product or system can be successfully installed and/or uninstalled in a specified environment.
- Replaceability - Degree to which a product can replace another specified software product for the same purpose in the same environment.

### Quality assurance/control activities
#### Activity 1: Adaptability, Installability Fulfillment
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

**Entry criterias**: Change in a code affects LLM or Embedding model logic. <!--What conditions must be met to start doing the activity. For example, if we are using SonarQube to ascertain maintainability, we might forego any recommendations in regards to lets say thread safety due to some reason, so entry criteria won't be met even if a trigger for the procedure (fall in rating) fired.-->

**Effort Estimation:** Estimated by the manager <!--What methodology could be used to estimate the amount of effort required. E.g. planning poker to estimate amount of work-hours that a developer spends-->

**Time-To-Resolution Estimation:** Adaptability issues can mostly be done during one week of one team member work, including few days of communication with the customer in cases regarding hardware discussion. <!--How to calculate amount of work-days to resolution. This is different from effort estimation because some resolutions require customer to handle some paperwork first-->

**The Procedure**: 
1. Gather updated specifications (LLM/Hardware/documentation updates).
2. Deploy the system within the updated specifications.
3. (In case of updated documentation) test the documentation upload functionality.
4. Run system with a basic input (e.g. "How to add the Bluetooth support?").
5. Validate system behavior (there is a response, output is consistent with the system behavior before the updates, all the documentation is taken into account).
<!--Describe the procedure undertaken. You may refer to other documents if necessary (for example, refer to Configuration Management if there a change in functional requirement requires a new feature to be fulfilled)-->

**Exit criterias**: 
- SonarQube score **≥A** for module independence.
- No errors during the testing.

#### Activity 2: Scalability Fulfillment
**Source**: Customer's business goal defines that the system should support up to 10 concurrent users. 
 <!--What is the cause for this activity. e.g. in case of Functional Compliance this is "Customer. Customer requires a certain level of functionality to be fulfilled"-->

**Triggers**: 
Customer wants to test the system with their test group.<!--What happens to trigger this procedure-->

**Conductor**: Vagif Khalilov, Developer <!--Who must handle this activity (Specify a person and their qualification)-->

**Training Required:** Load testing, LLM quantization techniques,  <!--What training should the person have undertaken before activity-->

**Measurements**: Hardware power required to support the 10 concurrent users. <!--What measurements reflect the efficiency of the activity-->

**Tools**: Gatling(load testing), Grafana(monitoring)  <!--What tools (software, browser extensions, etc) should be used-->

**Entry criterias**: LLM/embedding model changed, architecture changed. <!--What conditions must be met to start doing the activity. For example, if we are using SonarQube to ascertain maintainability, we might forego any recommendations in regards to lets say thread safety due to some reason, so entry criteria won't be met even if a trigger for the procedure (fall in rating) fired.-->

**Effort Estimation:** Estimated by the manager <!--What methodology could be used to estimate the amount of effort required. E.g. planning poker to estimate amount of work-hours that a developer spends-->

**Time-To-Resolution Estimation:** The time it takes to research LLM optimization and possible architecture improvements, and implement them (may take from 1 to 2 sprints). <!--How to calculate amount of work-days to resolution. This is different from effort estimation because some resolutions require customer to handle some paperwork first-->

**The Procedure**: 
1. Make sure the system is up and running.
2. Run system for a single user to get the standard performance metrics.
3. Note the response time and resource usage. Assess the model's response adequacy (did the answer satisfy the question by your own judgement?)
4. Test the system with the 10 users.
5. Repeat step 3.
6. Run same tests for the 30 mins.
7. Repeat step 3.
8. Compare the metrics for the one user 10 concurrent users and 10 concurrent users for prolonged time.
9. If load testing reveals metrics bottlenecks, bring up this issue with the team. <!--Describe the procedure undertaken. You may refer to other documents if necessary (for example, refer to Configuration Management if there a change in functional requirement requires a new feature to be fulfilled)-->

**Exit criterias**: All 10 users complete tasks without errors. Response times don't deviate under the tested load. System resource usage doesn't deviate from the usual one. <!--What conditions must be met to stop doing the activity-->


#### Activity 3: Replaceability Fulfillment
**Source**: Customer's business goal defines that the system must be able to connect with any of their resources (webpages, front-end clients, etc.). 
 <!--What is the cause for this activity. e.g. in case of Functional Compliance this is "Customer. Customer requires a certain level of functionality to be fulfilled"-->

**Triggers**: 
Customer wants to send a request to the system from a new resource..<!--What happens to trigger this procedure-->

**Conductor**: Vagif Khalilov, Developer <!--Who must handle this activity (Specify a person and their qualification)-->

**Training Required:** REST API knowledge, functional testing <!--What training should the person have undertaken before activity-->

**Measurements**: Time it takes to adapt to the system's API from a new resource. <!--What measurements reflect the efficiency of the activity-->

**Tools**: Swagger <!--What tools (software, browser extensions, etc) should be used-->

**Entry criterias**: API layer of the system changed <!--What conditions must be met to start doing the activity. For example, if we are using SonarQube to ascertain maintainability, we might forego any recommendations in regards to lets say thread safety due to some reason, so entry criteria won't be met even if a trigger for the procedure (fall in rating) fired.-->

**Effort Estimation:** Estimated by the manager <!--What methodology could be used to estimate the amount of effort required. E.g. planning poker to estimate amount of work-hours that a developer spends-->

**Time-To-Resolution Estimation** Must take into account Internet connection issues and access to the client's hardware(estimate time it usually takes for the client to respond either on the interview or via Telegram). Apart from that, the issue usually won't take more than 1-2 days of work. <!--How to calculate amount of work-days to resolution. This is different from effort estimation because some resolutions require customer to handle some paperwork first-->

**The Procedure**: 
1. Make sure that all the required functionality is accessible via Swagger page.
2. Run through the Swagger endpoints to make sure that the system responds without raising any errors.

**Exit criterias**: Swagger page is up and running. All the requested functionality is available via the system API. All the responses are consistent. <!--What conditions must be met to stop doing the activity-->


# Defect Management Process
## 1. Tools & Repositories
| Purpose | Repository | Artifacts                                      |  
|---------|------------|------------------------------------------------|  
| **Code Defects** | `https://github.com/OMP-Industrial-Project-Chat-Assistant/OMP-Chat-Assistant-Process` | Issues, Pull Requests, `bug`, `wontfix` labels |  
| **Documentation Defects** | `https://github.com/OMP-Industrial-Project-Chat-Assistant/OMP-Chat-Assistant-Process` | Issues, Pull Requests               |  

---

## 2. Defect Lifecycle  

### **1. Identification**  
**Where:** GitHub Issues in respective repo  
**Template:**  
```markdown
**Defect Type**: [Performance/Language/Docs]  
**Severity**: S1/S2/S3 (see below)  
**Repro Steps**:  
1. Query: "..."  
2. Actual: GPU usage 17.2GB  
3. Expected: ≤14.4GB per formula  

**Environment**:  
- AuroraOS Doc Version: 5.1.1-20240520  
- Model: `some-llm`  

**Evidence**:  
- `nvidia-smi` logs attached  
- Screenshot of Grafana (120s timeout)  
```

---

### **2. Triage**  
**Roles**:  
- **Code Defects**: Developer 
- **Docs Defects**: Developer, Manager 

**Process**:  

1. Priority assignment:  
   ```markdown
   /priority <S1|S2|S3>  
   /assign @developer-handle
   ```

**Severity Criteria**:  

| Label | Response SLA | GPU Impact |  
|-------|--------------|------------|  
| `S1` | >2min response | >14.4GB memory |  
| `S2` | Incorrect Russian | Broken doc links |
| `S3` | Code-style inconsistencies |  |

---

### **3. Fix Development**  
**Branch Naming Convention**:  
```bash
git checkout -b bug/{[chat/process]-#}/shortdesc
# Example: bug/chat-45/gpu-leak
```

**Code Requirements**:  
1. Must reference issue
2. Include verification test:

**Docs Requirements**:  
- Updates go to `https://github.com/OMP-Industrial-Project-Chat-Assistant/OMP-Chat-Assistant-Process/issues/{#}`

---

### **4. Verification**  
**Automated Checks**:  
- By running tests-job in CI.

**Manual Steps**:  
1. Assign to some of developer
2. Approve via PR review with:  
   ```diff
   + Verified: GPU memory now 12.8GB (issue #45)
   ```

---

### **5. Closure**  
**Requirements**:  
1. All checks pass  
2. Issue linked to PR  
3. Docs updated (for S1/S2)

# Process metrics definition
In general, the metrics of our quality are defined per quality assurance procedure (see procedures in Quality Assurance Activities section).

To ascertain the whole process quality, following metrics can be used:
| Metric | Description | Measure | Goal |
|--------|-------------|---------|------|
| Average TTR | Average time to resolution from defect discovery to closure | Days, Hours | <1 day |
| Average TTD | Average time to defect discovery. Github change history can show when the defect was introduced. | Days, Hours | <7 days |

Average TTR goal is justified by a somewhat tight timeline.

Average TTD goal is justified by the review frequency (See Quality plan) - the goal is to guarantee defect discovery within one review.

# Plan reconciliation and effort estimation

Current project plan expects approximately 67 story points of workload per sprint (2 weeks). Per our estimation (18 hours per member per week, for a total of 144 workhours, 1.4 hour per storypoint), we are capable of completing a total of 102 story points per week.

Per manager estimation and information provided from the procedures:
- Functional Suitability procedures require between 10 and 15 storypoints
- Performance procedures require between 4 and 8 storypoints
- Flexibility procedures require between 2 and 6 storypoints
- Maintainability procedures require between 2 and 6 storypoints
For a total of 35 story points in worst-case, and 18 story points in best-case, per sprint

Current plan can accomodate for up to 35 new story points per sprint, fitting the new procedures perfectly.

# Quality Plan

- Flexibility procedures are to be implemented on delivery of hardware (approx. end of May), and started from then on
- Performance procedures are to be implemented on delivery of hardware (approx. end of May), and started from then on
- Functional Suitability procedures are to be implemented on delivery of hardware (approx. end of May), and started from then on
- Maintainability procedures are to be implemented by the end of sprint 6 (May 30), and started from then on

The procedures are to be supplemented by a weekly review of the code and documentation, that is to cover any artifacts updated during the week.

The review is to be done during wrap-up meetings within our usual sprint cycle:


|            | Monday                    | Tuesday | Wednesday | Thursday        | Friday    |
| ---------- | ------------------------- | ------- | --------- | --------------- | --------- |
| **Week 1** | Task Distribution, Sprint | Sprint  | Sprint    | Sprint          | Wrap-up   |
| **Week 2** | Task Distribution, Sprint | Sprint  | Sprint    | Sprint, Wrap-up | Interview |
