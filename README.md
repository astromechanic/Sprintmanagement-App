# Sprintmanagement-App
A documentation for the app Sprintmanagement in my Dev Org

## Custom Objects with their Fields

### Employee__c

Field | Data Type
------|----------
Alias__c | Text(10)
Email__c | Email
Name | Text(80)
First_Name__c | Text(50)
Is_Active__c | Checkbox
Last_Name__c | Text(50)
Mobil__c | Text(50)
Num_of_Sprints__c | Roll-Up Summary (COUNT Sprint Assignment)

### Sprint__c

### Ticket__c

### SprintAssignment__c
An invisible junction object to connect `<Sprint__c>` and `<Employee__c>`.

### Timesheet_Item__c

## Processes

## Validation Rules
