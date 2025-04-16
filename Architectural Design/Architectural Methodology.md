# Introduction

**Version:** 1.0

**Last Edit:** 13.04.2025

**Last Editor:** Yaroslav Kim

**Owner:** Yaroslav Kim

**Approval Status:** N/A

**Type:** Process, architecture

**Description:** This document describes methodology for architectural design of this project.

**Dependencies:**
- [Business Context](<../Context and Requirements Management/EN/Context/Business Context.md>)
- [Modularity](<../Context and Requirements Management/EN/Requirements/Software Product Requirements.md#22-maintainability>)

# Justifications
- [Innopolis University](<../Context and Requirements Management/EN/Context/Business Context.md#4-business-constraintsdemands>) requires regorous approach to architectural design
- The development team requires a methodology for architectural design that allows for maximum [Modularity](<../Context and Requirements Management/EN/Requirements/Software Product Requirements.md#22-maintainability>). This approach allows for it.
- Lack of expertise - we could find the information on implementation of similar solutions, but the explanations were mostly very high-level, or focused on specifics of LLM optimization. Figuring out the best architecture bottom-up is not viable up-front.
- Iterative nature of development - the [customer](<../Context and Requirements Management/EN/Context/Business Context.md>) requires motivation in form of benefit shown, and this approach allows us to demonstrate benefit every iteration, gaining more justification for future investment of resources into this project every sprint.

# Content

## Methodology
Our team follows top-down approach to architectural design. 
The process is as follows:
1. For a system/subsystem, identify a list of highest-level subsystems.
2. If the subsystem is too low-level to be split into sub-systems, optimize it for fulfillment of:
	1. Functional Requirements
	2. Non-functional Requirements
3. Define their interaction between each other and optimize their interaction for fulfillment of:
	1. Functional Requirements
	2. Non-functional Requirements
4. Implement the system by implementing basic monolithic solution for each subsystem.
5. Once functional requirements are satisfied, identify subsystems on which step 1 can be applied and apply the process recursively.
1 recursive application of this method takes 2 sprints.

# Changelog
- v1.0 - 13.04.2025. Conversion to new format. Yaroslav Kim