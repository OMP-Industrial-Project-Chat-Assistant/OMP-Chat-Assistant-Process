# Quality Requirement Assurance Plan: Performance

## Quality Requirement Description
This characteristic represents the degree to which a product performs its functions within specified time and throughput parameters and is efficient in the use of resources (such as CPU, memory, storage, network devices, energy, materials...) under specified conditions. 
## Quality assurance/control activities
### Activity 1: Time Behaviour Fulfillment
**Source**: This characteristic has been defined during requirements elicitation on 1st interview. <!--What is the cause for this activity. e.g. in case of Functional Compliance this is "Customer. Customer requires a certain level of functionality to be fulfilled"-->

**Triggers**: The system takes more than 2 minutes to generate an answer for single test <!--What happens to trigger this procedure-->

**Conductor**: Kirill Korikov, Developer<!--Who must handle this activity (Specify a person and their qualification)-->

**Training Required:** general familiarity with LLM Quantization<!--What training should the person have undertaken before activity-->

**Measurements**: Time to response after question with context is provided to an LLM Controller <!--What measurements reflect the efficiency of the activity-->

**Tools**: IDE <!--What tools (software, browser extensions, etc) should be used-->

**Entry criterias**: The system consistently (3 times in a row) takes more than 2 minutes to generate an answer for a specific test. <!--What conditions must be met to start doing the activity. For example, if we are using SonarQube to ascertain maintainability, we might forego any recommendations in regards to lets say thread safety due to some reason, so entry criteria won't be met even if a trigger for the procedure (fall in rating) fired.-->

**Effort Estimation:** planning poker, or independent research by assignee <!--What methodology could be used to estimate the amount of effort required. E.g. planning poker to estimate amount of work-hours that a developer spends-->

**Time-To-Resolution Estimation:** amount of days equal estimated amount of hours divided by two (assuming 2 hours per day of work put in) <!--How to calculate amount of work-days to resolution. This is different from effort estimation because some resolutions require customer to handle some paperwork first-->

**The Procedure**: Follow the [Contribution Guidelines](<Configuration Management/Contribution Guidelines.md>) to raise a new `fix` issue. Assign it to current sprint. Conduct quantization until the issue is resolved. <!--Describe the procedure undertaken. You may refer to other documents if necessary (for example, refer to Configuration Management if there a change in functional requirement requires a new feature to be fulfilled)-->

**Exit criterias**: The system consistently (3 times in a row) takes less than 2 minutes to generate an answer for a specific test. <!--What conditions must be met to stop doing the activity-->
