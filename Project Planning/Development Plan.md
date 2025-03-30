**Last Updated**: March 30th, 2025
**Version**: 1.2

Note: Development plan might be out of date, if there are changes in the project timeline

Here’s the development plan formatted as a table with **functionality-driven phases**, **2-week sprints**, and **demo milestones**:

| Sprint | Dates           | Key Functionality Achieved                                                                                            | Demo Focus                                                                                                                              | Status      | Milestone                  |
| ------ | --------------- | --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- | ----------- | -------------------------- |
| **1**  | Mar 10 – Mar 21 | - Basic API endpoint operational<br>- Russian-only response generation                                                | - Show API request/response flow<br>- Demonstrate basic functionality of asking questions/obtaining answers<br>                         | Done        | Prototype Delivery         |
| **2**  | Mar 24 – Apr 4  | - Source URL citations in answers<br>- Compile research on quantization<br>- CI finalized                             | - Demonstrate source attribution in answers<br>- Display crawled files from AuroraOS and GitLab repos<br>- Provide quantization options | Done        |                            |
| **3**  | Apr 7 – Apr 18  | - Response time reduced to 3 minutes<br>- Support 3 concurrent users<br>- Documentation crawler for omprussia sources | - Compare response times (5m → 3m)<br>- Simulate 3 parallel requests<br>- Expanded content of LLM coverage                              | In-progress |                            |
| **4**  | Apr 21 – May 2  | - Dockerized components<br>- Load balancing for 6 users                                                               | - Deploy on test cluster<br>- Simulate 6-user load test                                                                                 | Planned     |                            |
| **5**  | May 5 – May 16  | - Initial UAT passed<br>- ≤2-minute response SLA achieved<br>- Draft Russian user docs                                | - Formal performance benchmark<br>- Walk through documentation draft                                                                    | Planned     | MVP Delivery               |
| **6**  | May 19 – May 30 | - Live monitoring dashboard (Grafana)<br>- Health alerts in Russian                                                   | - Display real-time metrics<br>- Simulate and recover from a failure                                                                    | Planned     | Pre-final product delivery |
| **7**  | Jun 2 – Jun 13  | - UAT passed with real queries<br>- Final Russian docs approved                                                       | - Customer-submitted query test<br>- Documentation sign-off                                                                             | Planned     |                            |
| **8**  | Jun 16 – Jun 27 | - One-click deployment scripts<br>- Disaster recovery plan                                                            | - Deploy system in 5 minutes<br>- Test rollback procedure                                                                               | Planned     | Final product delivery     |
| **9**  | Jun 30 – Jul 11 | In case of delays, this sprint is considered backup                                                                   |                                                                                                                                         | Backup      |                            |
| **10** | Jul 14 – Jul 25 | In case of delays, this sprint is considered backup                                                                   |                                                                                                                                         | Backup      |                            |
| 11     | Jul 28 - Aug 8  | In case of delays, this sprint is considered backup                                                                   |                                                                                                                                         | Backup      |                            |
| 12     | Aug 11 - Aug 22 | In case of delays, this sprint is considered backup                                                                   |                                                                                                                                         | Backup      |                            |


---

**Notes:**  
1. **Demo Alignment:** Each sprint concludes with a working demo of the functionality achieved.  
2. **Customer Touchpoints:** Demos occur every 2 weeks (last day of each sprint).  
3. 33% of backup time is taken per assumption of possible 50% delay due to inexperience of the team. Supporting research:
	- https://www.researchgate.net/publication/312530233_Predicting_the_delay_of_issues_with_due_dates_in_software_projects/download
**Last Approved version:** *
**Approved by:** AWAITING APPROVAL
**Revision History:** 
- 1.0 Initial high-level plan devised via Github projects
- 1.1 Detailed project plan as Markdown table
- 1.2 Second sprint is over 