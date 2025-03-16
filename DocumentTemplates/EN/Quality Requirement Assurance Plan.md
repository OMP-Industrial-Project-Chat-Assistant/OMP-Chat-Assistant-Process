The following is a template of quality requirement assurance plan for a single quality requirement
```Markdown
# Quality Requirement Assurance Plan

## Quality Requirement Description
<!--A short description of the quality requirement. Example: "Maintainability is our capacity to change the system..."-->
## Quality assurance/control activities
### Activity 1
**Source**: <!--What is the cause for this activity. e.g. in case of Functional Compliance this is "Customer. Customer requires a certain level of functionality to be fulfilled"-->
**Triggers**: <!--What happens to trigger this procedure-->
**Conductor**: <!--Who must handle this activity (Specify a person and their qualification)-->
**Training Required:** <!--What training should the person have undertaken before activity-->
**Measurements: <!--What measurements reflect the efficiency of the activity-->
Tools**: <!--What tools (software, browser extensions, etc) should be used-->
**Entry criterias**: <!--What conditions must be met to start doing the activity. For example, if we are using SonarQube to ascertain maintainability, we might forego any recommendations in regards to lets say thread safety due to some reason, so entry criteria won't be met even if a trigger for the procedure (fall in rating) fired.-->
**Effort Estimation:** <!--What methodology could be used to estimate the amount of effort required. E.g. planning poker to estimate amount of work-hours that a developer spends-->
**Time-To-Resolution Estimation:** <!--How to calculate amount of work-days to resolution. This is different from effort estimation because some resolutions require customer to handle some paperwork first-->
**The Procedure**: <!--Describe the procedure undertaken. You may refer to other documents if necessary (for example, refer to Configuration Management if there a change in functional requirement requires a new feature to be fulfilled)-->
**Exit criterias**: <!--What conditions must be met to stop doing the activity-->
```
