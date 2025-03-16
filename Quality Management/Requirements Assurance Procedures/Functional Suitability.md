# Quality Requirement Assurance Plan: Functional Suitability

## Quality Requirement Description
This characteristic represents the degree to which a product or system provides functions that meet stated and implied needs when used under specified conditions. 
## Quality assurance/control activities
### Activity 1: Functional Correctness Fulfillment
**Source**: Customer set out a certain level of functionality to fulfill <!--What is the cause for this activity. e.g. in case of Functional Compliance this is "Customer. Customer requires a certain level of functionality to be fulfilled"-->
**Triggers**: Requirements elicitation caused a change in definition of functional correctness<!--What happens to trigger this procedure-->
**Conductor**: Yaroslav Kim, Manager
<!--Who must handle this activity (Specify a person and their qualification)-->
**Training Required:** Varies<!--What training should the person have undertaken before activity-->
**Measurements**: Customer approval of renewed requirements/development plan<!--What measurements reflect the efficiency of the activity-->
**Tools**: Github, any Markdown editor <!--What tools (software, browser extensions, etc) should be used-->
**Entry criterias**: Customer has changed requirements in a way that requires formulation of a new requirement/reformulation of old requirement/removal of old requirement <!--What conditions must be met to start doing the activity. For example, if we are using SonarQube to ascertain maintainability, we might forego any recommendations in regards to lets say thread safety due to some reason, so entry criteria won't be met even if a trigger for the procedure (fall in rating) fired.-->
**Effort Estimation:** Planning poker <!--What methodology could be used to estimate the amount of effort required. E.g. planning poker to estimate amount of work-hours that a developer spends-->
**Time-To-Resolution Estimation:** Reevaluate the long-term plan and assign the issue to one of the sprints. <!--How to calculate amount of work-days to resolution. This is different from effort estimation because some resolutions require customer to handle some paperwork first-->
**The Procedure**: Follow the [Contribution Guidelines](<Configuration Management/Contribution Guidelines.md>) to raise a new `task` issue involving updates to requirements documentation and all other relevant documents. Assign it to current sprint and fulfill until the next sprint starts. Send documents meant for customer reading to the customer for approval. <!--Describe the procedure undertaken. You may refer to other documents if necessary (for example, refer to Configuration Management if there a change in functional requirement requires a new feature to be fulfilled)-->
**Exit criterias**: Once the customer has approved the new documentation, consider the `task` issue resolved <!--What conditions must be met to stop doing the activity-->
### Activity 2: Functional Correctness Fulfillment
**Source**: Customer set out a certain level of functionality to fulfill<!--What is the cause for this activity. e.g. in case of Functional Compliance this is "Customer. Customer requires a certain level of functionality to be fulfilled"-->
**Triggers**: A valid question is not answered by the system, or answered incorrectly <!--What happens to trigger this procedure-->
**Conductor**: Varies
- Kirill Korikov in case the issue is LLM aquity related
- Akam T. in case the issue is related to inability of database to provide required context
- Vagif Khalilov in case the issue is related to improper prompting of other modules
- Yaroslav Kim in case the issue is related to lack of sources available to system
<!--Who must handle this activity (Specify a person and their qualification)-->
**Training Required:** Varies <!--What training should the person have undertaken before activity-->
**Measurements**: The reporter's rating of the given answer, and perceived similarity to of given answer to expected answer. <!--What measurements reflect the efficiency of the activity-->
**Tools**: IDE <!--What tools (software, browser extensions, etc) should be used-->
**Entry criterias**: A case of valid question being not answered or answered incorrectly is reported and recreated <!--What conditions must be met to start doing the activity. For example, if we are using SonarQube to ascertain maintainability, we might forego any recommendations in regards to lets say thread safety due to some reason, so entry criteria won't be met even if a trigger for the procedure (fall in rating) fired.-->
**Effort Estimation:** Manager calculated prediction <!--What methodology could be used to estimate the amount of effort required. E.g. planning poker to estimate amount of work-hours that a developer spends-->
**Time-To-Resolution Estimation:** Estimated time divided by amount of daily hours of work per assignee. In case the issue is connected to lack of sources that need to be requested from customer - add another week to account for customer's process velocity <!--How to calculate amount of work-days to resolution. This is different from effort estimation because some resolutions require customer to handle some paperwork first-->
**The Procedure**: Follow the [Contribution Guidelines](<Configuration Management/Contribution Guidelines.md>) to raise a new `fix` issue. Assign it to current sprint. Conduct collective research on the problem to determine proper assignee. Resolve the issue. <!--Describe the procedure undertaken. You may refer to other documents if necessary (for example, refer to Configuration Management if there a change in functional requirement requires a new feature to be fulfilled)-->
**Exit criterias**: The question is answered correctly <!--What conditions must be met to stop doing the activity-->

