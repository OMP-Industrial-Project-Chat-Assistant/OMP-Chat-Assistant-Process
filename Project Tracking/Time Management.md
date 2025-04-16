# Introduction

**Version:** 1.0

**Last Edit:** 13.04.2025

**Last Editor:** Yaroslav Kim

**Owner:** Yaroslav Kim

**Approval Status:** N/A

**Type:** Process

**Description:** This document describes how the 

**Dependencies:**
- [Business Context](</Context and Requirements Management/EN/Context/Business Context.md>)

# Justifications
- The project must be completed in timely manner. To achieve that, procedures need to be implemented to understand if it will be the case.
- The time spent on project must be logged per [Innopolis University requirements](/Context%20and%20Requirements%20Management/EN/Context/Business%20Context.md)

# Content
## Planning Poker
- When a new development issue is formed, the manager calls for planning poker using https://planningpokeronline.com/
- All members are to provide a response within a reasonable time (usually 6 hours)
- The manager takes the average and multiplies it by average mistake ratio in this category - this is the predicted amount of time to be spent on the issue

Current average mistake ratio: 1
## How to track time
### Before you start
Before you start, you need to:
- Be registered on [Clockify](https://clockify.me/)
- Add an [extension for your browser](https://clockify.me/apps)
- Log in in the extension
- Accept invitation to workspace in your mail
### How to track your time
If all works correctly, click on the "Start Timer" when you open an issue
![image](<../Pictures/Pasted image 20250303191110.png>)
Choose OMP Chat Assistant project, appropriate task, and appropriate tag in the context menu, then click DONE
![image](<../Pictures/Pasted image 20250303191214.png>)
Once you stop working, click "Stop Timer" in the issue, or in the extension options
![image](<../Pictures/Pasted image 20250303191353.png>)
### How to add time retroactively
Open clockify workspace and go to calendar
![image](<../Pictures/Pasted image 20250303192017.png>)
Click on an empty space in the calendar and fill out the form in the pop-up, then click "Done"
![image](<../Pictures/Pasted image 20250303192101.png>)

## How to track status
### Time Tracking Information On Each Issue
Every open issue has the following information:
- `X` Amount of hours predicted
- `Y` Amount of actual hours spent
- `Z` Self-reported completion status (0-100)
### Short Term Predictions
Short term predictions are based strongly on self-reported progress on issues. 

Whether we are on time on particular issue, is determined as follows:
- Calculate the remaining work time in the sprint, assuming the assignee dedicates 2 hours per day to work on the issue:
	- `R = DaysUntilEnd * 2.0`
- Figure out how much time a single percent of progress takes:
	- `F = Y/Z`
- Figure out estimation of remaining work based on cost of percent of progress
	- `W = (100 - Z) * F`
- If `W` is more than `R`, then we are not on time. Otherwise - we are on time.
### Long Term Predictions
Long term predictions are based around current development plan.
- Every 4 issues that get delayed account for one sprint of delay (issue per team member)
- We have a margin of delay equal to 4 sprints (Course ends in late August)

# Changelog
- v1.0. 13/04/2025 - conversion of document to current format, and consolidation by Yaroslav Kim.