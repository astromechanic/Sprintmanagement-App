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


Name | Object | Description | Status | Comments
-----|--------|------------|-------- | --------
Sprint Assignment | Sprint Assignment | Send an email to Employee when he or she has been assigned to a Sprint | Active 
Update Contacts | Account | Update child Contact addresses when an account's shipping address is updated. | Inactive
Notify an Employee when a Sprint Assignment deleted | Employee | Sent an email to Employee when a Sprint Assignment was deleted. An Employee gets a text email without specifying the Sprint name. Send Custom Notification to Current User withot specifying the Sprint Name | Inactive | Possibly not an option at all
Sprint Assignment Deleted (test version) | Sprint | Send Custom Notification to Current User with the Sprint Name | Active | How to get the right recipient??



# Flows

Name | Description | Status
-----|-------------|---------
Sprint Assignment Email Notification| Send an email to an employee when he or she has been assigned to a sprint. The flow executes the same actions as the process 'Sprint Assignment' | Inactive

