# Some Query Expression examples

### Portfolio items with specific text in the name
```
Name contains "Technical Debt"
```

### Portfolio items with a specific investment category
```
InvestmentCategory = "Cost Savings"
```

### Portfolio items with a specific custom field value
```
c_MyCustomField = "MyCustomValue"
```

### Unscheduled features
```
Release = null
```

### Features in current release
```
Release.ReleaseStartDate <= today AND Release.ReleaseDate >= today
```

### Leaf user stories attached to features in current release',
```
Feature.Release.ReleaseStartDate <= today AND Feature.Release.ReleaseDate >= today AND DirectChildrenCount = 0
```

### Scheduled for a release',
```
Release.Name = "PSI 2013.Q1"
```

### Portfolio items with a specific parent',
```
Parent.Name = "Design new login page"
```

### Portfolio items with no parent',
```
Parent = null
```

### Portfolio items with no child portfolio items or user stories',
```
DirectChildrenCount = "0"
```

### Portfolio items that have a state other than Discovering Or Done',
```
State.Name != Discovering AND State.Name != Done
```

### Portfolio items that have Total Completion Percent (by story count) of 50% or less',
```
PercentDoneByStoryCount <= ".50"
```

### Portfolio items that do not have tags that contain specific text',
```
Tags.Name !contains "Blue"
```

### Portfolio items with two tags: Red and Blue',
```
Tags.Name = "Blue" AND Tags.Name = "Red"
```

### Portfolio items with three tags: Red, Blue and Green',
```
Tags.Name = "Blue" AND Tags.Name = "Red" AND Tags.Name = "Green"
```

### Portfolio items owned by Mike or Sally',
```
Owner.UserName = "mike@acme.com" OR Owner.UserName = "sally@acme.com"
```

### Portfolio items that have an Actual Start Date after November 5, 2012',
```
ActualStartDate > "2012-11-05"
```

### Portfolio items that have a Planned Start Date later than last week',
```
PlannedStartDate > "lastweek"
```

### Portfolio items that have a Planned Start Date later than last week (alternative)',
```
PlannedStartDate > "today - 7"
```

### Portfolio items that have planned dates, but not all associated user stories are finished',
```
PlannedStartDate != null AND PlannedEndDate != null AND PercentDoneByStoryCount <= ".50"
```

### Filter Out Features With No State Or Archived Features',
```
Tags.Name = "RPM" AND State.Name != null AND State.Name != "Archived"
```

### Portfolio items in progress',
```
PercentDoneByStoryCount > 0 AND PercentDoneByStoryCount < 1
```

### Portfolio items that have stories in progress but nothing has been accepted yet',
```
ActualStartDate != null AND ActualEndDate = null
```

### Finished portfolio items',
```
ActualStartDate != null AND ActualEndDate != null
```

### Recent portfolio items and portfolio items in progress',
```
(ActualStartDate != null AND ActualEndDate = null) OR (ActualStartDate != null AND ActualEndDate = LastQuarter)
```

### Work items with specific text in the name',
```
Name contains "Technical Debt"
```

### Work items in a specific iteration (by name)',
```
Iteration.Name = "September Sprint 2"
```

### User stories without parent user stories',
```
Parent = null
```

### User stories that have parents, but they are not portfolio items',
```
PortfolioItem = null AND Parent != null
```

### User stories that have parents which are either user stories or feature-level portfolio items',
```
PortfolioItem != null OR Parent != null
```

### Open defects',
```
State < "Closed"
```

### User stories needing estimates',
```
PlanEstimate = null AND ScheduleState = "Defined"
```

### User stories in an iteration needing estimates',
```
PlanEstimate = null AND ScheduleState = "Defined" AND Iteration != null
```

### User stories with a schedule state value between Defined and Accepted',
```
ScheduleState > "Defined" AND ScheduleState < "Accepted"
```

### User stories without defects',
```
Defects.ObjectID = null
```

### User stories with defects',
```
Defects.ObjectID != null
```

### My tasks in the current iteration',
```
Owner.UserName = {Me} AND Iteration.StartDate <= today AND Iteration.EndDate >= today
```

### Open defects, owned by Bob, associated to a specific user story',
```
Owner.UserName = "bob@dobalina.com" and State < "Closed" and Requirement.Name = "Story 2"
```

### Open defects George found',
```
SubmittedBy.UserName = "george@vandelayindustries.com" and State != "Closed"
```

### Defects without tags',
```
Tags.ObjectID = null
```

### Defects that have tags',
```
Tags.ObjectID != null
```

## Notes related to dates
Tip: Use the following date variables and date expressions: today, yesterday, tomorrow, lastweek, nextweek, lastmonth, nextmonth, lastquarter, nextquarter, lastyear, next year, today + , and today - . For examples and usage details, see Date Variables.
