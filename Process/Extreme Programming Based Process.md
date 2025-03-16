The process is based around Extreme Programming. The process consists of 4 activities:
- Task distribution
- Sprint
- Wrap-up
- Interview

Activities will follow a 2-week cycle pattern, depending on whether an interview is organized on that week or not.

|            | Monday                    | Tuesday | Wednesday | Thursday        | Friday    |
| ---------- | ------------------------- | ------- | --------- | --------------- | --------- |
| **Week 1** | Task Distribution, Sprint | Sprint  | Sprint    | Sprint          | Wrap-up   |
| **Week 2** | Task Distribution, Sprint | Sprint  | Sprint    | Sprint, Wrap-up | Interview |

Saturday and Sunday are considered rest days for everyone 
# Task Distribution
This activity only starts after product requirements (if new are available) have been confirmed by the customer.
This activity is when the assigned manager distributes the tasks between team members.
- An issue is opened on github with a member assigned. All issues must follow [Contribution Guidelines](<Configuration Management/Contribution Guidelines.md>)
- The member is notified via telegram about the new task.
- All members are required to rate the issue laboriousness via planning poker. Manager will provide the appropriate link right after assigning the issue

Developer may appeal the task distribution fairness to the manager. If another developer supports this appeal, the relevant github issues will be changed by the manager to reflect the change in distribution of tasks.

It is the manager's responsibility to ensure that task distribution is done on Monday. All prep for that is done on Saturday and Sunday.
# Sprint
Sprint is a multi-day activity that starts after Task Distribution. During a sprint, all developers work on their assigned tasks. 
- All developers must update their time spent and self-reported estimation of progress in the issues they are assigned to in the project fields for this issue
- All developers must track the time they spend on tasks. [How To Track Time](<How To Track Time.md>)
- All developers must follow [Contribution Guidelines](<Configuration Management/Contribution Guidelines.md>), which includes but not limited to:
	- Branch naming conventions
	- Issue and pull request templates
# Wrap-up
Wrap-up is an activity meant for the team to figure out their status at the end of the sprint. It is either done via a telegram chat, or on a meeting.
- Every team member is requested to provide usable artifacts that were produced within this week
- Every team member raises their concerns in case such are present.
- Manager and another russian-speaking team member formulate the next [Pre-Interview Document](<Pre-Interview Document.md>) from the information gathered and put the document in `Context and Requirements Management/EN/Pre-Interview Documents`.
In total this activity should take up to 1.5 hours.
# Interview
Depending on customer availability, an interview is called. During the interview, the following is done:
- All demos are demonstrated by Interviewer A
	- Customer comments are recorded by Interviewer B.
- Questions from [Pre-Interview Document](<Pre-Interview Document.md>) are asked being asked by Interviewer A.
	- Every answer is recorded by Interviewer B.
- Further clarifications are asked by Interviewer A and Interviewer B
- Once all questions by both Interviewers and the customers are exceeded, the meeting is concluded
- Manager produces [Post-Interview Document](<DocumentTemplates/EN/Post-Interview Document.md>) and puts it in `Context and Requirements Management/EN/Post-Interview Documents`
- Manager then updates relevant documents per [Requirements Elicitation Document](<Context and Requirements Management/EN/Requirements Elicitation>)
After the interview, the manager formulates all changes to the requirements and sends them to customer for approval following the [Requirements Policy](<Requirements Policy.md>)
