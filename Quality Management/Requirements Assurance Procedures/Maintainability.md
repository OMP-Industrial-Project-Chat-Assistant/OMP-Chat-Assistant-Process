# Introduction

**Version:** 1.0

**Last Edit:** 13.04.2025

**Last Editor:** Yaroslav Kim

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

# Quality Requirement Assurance Plan: Maintainability

## Quality Requirement Description
This characteristic represents the degree of effectiveness and efficiency with which a product or system can be modified to improve it, correct it or adapt it to changes in environment, and in requirements. 
## Quality assurance/control activities
### Activity 1: Modularity Fulfillment
**Source**: The development team requires a degree of modularity that allows parallel independent work on different modules of the system. <!--What is the cause for this activity. e.g. in case of Functional Compliance this is "Customer. Customer requires a certain level of functionality to be fulfilled"-->

**Triggers**: A change introduced in a module led to unexpected failure of the system <!--What happens to trigger this procedure-->

**Conductor**: Vagif Khalilov, Developer <!--Who must handle this activity (Specify a person and their qualification)-->

**Training Required:** Basics of networking, architectural design <!--What training should the person have undertaken before activity-->

**Measurements**: Time to resolution <!--What measurements reflect the efficiency of the activity-->

**Tools**: IDE, draw.io <!--What tools (software, browser extensions, etc) should be used-->

**Entry criterias**: A change introduced in a module led to unexpected failure of the system, that has been identified by one of the team member as an issue of modularity <!--What conditions must be met to start doing the activity. For example, if we are using SonarQube to ascertain maintainability, we might forego any recommendations in regards to lets say thread safety due to some reason, so entry criteria won't be met even if a trigger for the procedure (fall in rating) fired.-->

**Effort Estimation:** Planning poker <!--What methodology could be used to estimate the amount of effort required. E.g. planning poker to estimate amount of work-hours that a developer spends-->

**Time-To-Resolution Estimation:** Architectural issues are considered serious enough to require full sprint unless proven otherwise <!--How to calculate amount of work-days to resolution. This is different from effort estimation because some resolutions require customer to handle some paperwork first-->

**The Procedure**: Follow the [Contribution Guidelines](</Configuration Management/Contribution Guidelines.md>) to raise a new `fix` issue. Assign it to current sprint. Reevaluate current architecture, propose changes to architecture, raise `fix` issues with appropriate assignees to update the modules, update the architectural diagrams. <!--Describe the procedure undertaken. You may refer to other documents if necessary (for example, refer to Configuration Management if there a change in functional requirement requires a new feature to be fulfilled)-->

**Exit criterias**: The development team has reached a strict majority agreement that modularity requirement has been fulfilled. <!--What conditions must be met to stop doing the activity-->


# Changelog
- v1.3 13/04/2025 - conversion of document to current format by Yaroslav Kim

