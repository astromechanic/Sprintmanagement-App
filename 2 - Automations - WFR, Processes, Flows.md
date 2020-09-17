# Validation Rules

Name | Object | Field | Description
-----|--------|------------|---------
Today_or_earlier | Timesheet_Item__c | Day__c | Prevents a user to save a timesheet item record on the future day  

# Workflow Rules

Name | Object | Description | Status
-----|--------|------------|---------
Sprint Assignment Unique ID | Sprint Assignment | Prevent one employee to be assigned more than once to one sprint | Active
NoStatusChangeLast30Days | Opportunity | Send an email when an opportunity was not updated within last 30 days | Inactive

# Processes


Name | Object | Description | Status
-----|--------|------------|--------
Sprint Assignment | Sprint Assignment | Send an email to Employee when he or she has been assigned to a Sprint | Inactive 

```diff
- Много версий процесса, которые отличаются условиями: разобраться, какой процесс за что отвечает и убрать ненужное!
```

# Flows

Name | Description | Status
-----|-------------|---------
Sprint Assignment Email Notification| Send an email to an employee when he or she has been assigned to a sprint. The flow executes the same actions as the process 'Sprint Assignment' | Inactive

