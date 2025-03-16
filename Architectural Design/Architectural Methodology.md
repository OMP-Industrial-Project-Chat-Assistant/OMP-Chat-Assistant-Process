# Methodology
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

# Rationale
We decided on this approach for the following reasons:
- Lack of expertise - we could find the information on implementation of similar solutions, but the explanations were mostly very high-level, or focused on specifics of LLM optimization. Figuring out the best architecture bottom-up is not viable up-front.
- Iterative nature of development - the customer requires motivation in form of benefit shown, and this approach allows us to demonstrate benefit every iteration, gaining more justification for future investment of resources into this project every sprint.