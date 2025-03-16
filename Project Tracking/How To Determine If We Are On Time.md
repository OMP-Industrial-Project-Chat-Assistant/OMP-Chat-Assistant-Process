# Time Tracking Information On Each Issue
Every open issue has the following information:
- `X` Amount of hours predicted
- `Y` Amount of actual hours spent
- `Z` Self-reported completion status (0-100)
# Short Term Predictions
Short term predictions are based strongly on self-reported progress on issues. 

Whether we are on time on particular issue, is determined as follows:
- Calculate the remaining work time in the sprint, assuming the assignee dedicates 2 hours per day to work on the issue:
	- `R = DaysUntilEnd * 2.0`
- Figure out how much time a single percent of progress takes:
	- `F = Y/Z`
- Figure out estimation of remaining work based on cost of percent of progress
	- `W = (100 - Z) * F`
- If `W` is more than `R`, then we are not on time. Otherwise - we are on time.
# Long Term Predictions
Long term predictions are based around current development plan.
- Every 4 issues that get delayed account for one sprint of delay (issue per team member)
- We have a margin of delay equal to 4 sprints (Course ends in late August)
