# Sprintmanagement-App
A documentation for the app Sprintmanagement in my Dev Org

## Custom Objects with their Fields

### Employee__c

Field | Data Type | Description (optional)
------|----------|------------------------
Alias__c | Text(10) |
Email__c | Email |
Name | Text(80) |
First_Name__c | Text(50) |
Is_Active__c | Checkbox |
Last_Name__c | Text(50) |
Mobil__c | Text(50) |
Num_of_Sprints__c | Roll-Up Summary (COUNT Sprint Assignment) |

### Sprint__c

Field | Data Type | Description (optional)
------|----------|------------------------
Estimated_effort_PD__c | Roll-Up Summary (SUM Ticket) |
Goal__c | Long Text Area(32768) |
Num_of_Tickets__c | Roll-Up Summary (COUNT Ticket) |
Name | Text(80) | 
Status__c | Picklist | New, Running, Finished


### Ticket__c

Field | Data Type | Description (optional)
------|----------|------------------------
Assigned_to__c | Lookup(Employee)
Effort_data_model__c	| Number(16, 2)	
Effort_deployment__c	Number(16, 2)	
Effort_documentation__c	Number(16, 2)		
Effort_programming__c	Number(16, 2)
Effort_specification__c	Number(16, 2)		
Effort_testing__c	Number(16, 2)	
Estimated_effort__c	Number(16, 2)		
Estimated_effort_PD__c	Formula (Number)
Estimation_comments__c	Long Text Area(32768)
Internal_estimate__c	Formula (Number)
Sprint__c	Master-Detail(Sprint)		
Status__c	Picklist	
Name	Text(80)	
Working_Package_Name__c	Formula (Text)

### SprintAssignment__c
An invisible junction object to connect `<Sprint__c>` and `<Employee__c>`.

### Timesheet_Item__c

## Processes

## Validation Rules
