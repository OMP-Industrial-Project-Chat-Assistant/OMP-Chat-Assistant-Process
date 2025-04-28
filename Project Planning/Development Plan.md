# Introduction

**Version:** 1.4

**Last Edit:** 27.04.2025

**Last Editor:** Yaroslav Kim

**Owner:** Yaroslav Kim

**Approval Status:** AWAITING APPROVAL

**Type:** Planning

**Description:** This document describes the overall plan of the project development

**Dependencies:**
- [Business Context](</Context and Requirements Management/EN/Context/Business Context.md>)
- [Requirements](</Context and Requirements Management/EN/Requirements/Software Product Requirements.md>)

# Justifications
- The plan is limited by the course duration.
- The plan starts in March due to issues with scheduling in February.
- [Satisfy Innopolis University need for process visibility](</Context and Requirements Management/EN/Context/Business Context.md>)
- Satisfy the developer need for consistency in results

# Content
Note: Development plan might be out of date, if there are changes in the project timeline

Here’s the development plan formatted as a table with **functionality-driven phases**, **2-week sprints**, and **demo milestones**:

| Sprint | Dates           | Key Functionality Achieved                                                                                                                                                        | Demo Focus                                                                                                                                             | Status      | Milestone                  | Note                                                                                         | Story points (Approximation) |
| ------ | --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------- | -------------------------- | -------------------------------------------------------------------------------------------- | ---------------------------- |
| **1**  | Mar 10 – Mar 21 | - Basic API endpoint operational (12)<br>- Russian-only response generation (12)                                                                                                  | - Show API request/response flow<br>- Demonstrate basic functionality of asking questions/obtaining answers<br>                                        | Done        | Prototype Delivery         |                                                                                              | 24                           |
| **2**  | Mar 24 – Apr 4  | - Source URL citations in answers (12)<br>- CI finalized (12)                                                                                                                     | - Demonstrate source attribution in answers<br>- Display crawled files from AuroraOS and GitLab repos<br>                                              | Done        |                            |                                                                                              | 24                           |
| **3**  | Apr 7 – Apr 18  | ~~- Response time reduced to 3 minutes (12)~~<br>- Compile research on quantization (12)<br>- Support 3 concurrent users (12)<br>~~-Documentation crawler for omprussia sources~~ | - Compare response times (5m → 3m)<br>~~- Simulate 3 parallel requests~~<br>- Provide quantization options<br>~~- Expanded content of LLM coverage~~   | Done        |                            | Documentation crawling is delayed until the database embedding is optimized                  | 24                           |
| **4**  | Apr 21 – May 2  | - Produce architecture for load balancing (12).<br>- Produce a deployment plan (12)<br>- Produce a testing plan (8)                                                               | Architecture for load-balanced multiple user solution is complete. Basic testing mechanism is implemented. Can deploy on machine provided by customer. | In-Progress |                            | Discoveries made to LLM quantization. Potentially no longer need to optimize LLM performance | 32                           |
| **5**  | May 5 – May 16  | - Implement new architecture (12) <br>- Deploy on provided machine (12)<br>                                                                                                       | - System is deployed and can serve testers<br>                                                                                                         | Planned     |                            |                                                                                              | 24                           |
| **6**  | May 19 – May 30 | - Implement basic testing of overall system (18)<br>- Gather and organize feedback from any testers (6)                                                                           | - 100% meaningful code coverage from tests<br>- Tests successfully catch obviously faulty response (imagination, when no context is available)         | Planned     | MVP Delivery               |                                                                                              | 24                           |
| **7**  | Jun 2 – Jun 13  | - Optimize embedding and database to guarantee fast (1 minute) response from whole system (24)<br>-Documentation crawler for omprussia sources (12)                               | - Embedding is optimized and database lookup/edits are faster<br>- Expanded content of LLM coverage                                                    | Planned     |                            |                                                                                              | 36                           |
| **8**  | Jun 16 – Jun 27 | - Live monitoring dashboard (Grafana) (12)<br>- Health alerts in Russian (6)<br>- Draft Russian user docs (6)                                                                     | - Display real-time metrics<br>- Simulate and recover from a failure<br>- Walk through documentation draft                                             | Planned     | Pre-final product delivery |                                                                                              | 24                           |
| **9**  | Jun 30 – Jul 11 | - User tests passed with real queries (12)<br>- Final Russian docs approved (12)                                                                                                  | - Customer-submitted query test<br>- Documentation sign-off                                                                                            | Planned     |                            |                                                                                              | 24                           |
| **10** | Jul 14 – Jul 25 | - One-click deployment scripts (12)<br>- Disaster recovery plan (12)                                                                                                              | - Deploy system in 5 minutes<br>- Test rollback procedure                                                                                              | Planned     | Final product delivery     |                                                                                              | 24                           |
| 11     | Jul 28 - Aug 8  | In case of delays, this sprint is considered backup                                                                                                                               |                                                                                                                                                        | Backup      |                            |                                                                                              |                              |
| 12     | Aug 11 - Aug 22 | In case of delays, this sprint is considered backup                                                                                                                               |                                                                                                                                                        | Backup      |                            |                                                                                              |                              |


---

**Notes:**  
1. **Demo Alignment:** Each sprint concludes with a working demo of the functionality achieved.  
2. **Customer Touchpoints:** Demos occur every 2 weeks (last day of each sprint).  
3. 33% of backup time is taken per assumption of possible 50% delay due to inexperience of the team. Supporting research:
	- https://www.researchgate.net/publication/312530233_Predicting_the_delay_of_issues_with_due_dates_in_software_projects/download

# Changelog
- v1.4 Reorganized plan and assigned point weight to every task
- v1.2 Second sprint is over 
- v1.1 Detailed project plan as Markdown table
- v1.0 Initial high-level plan devised via Github projects