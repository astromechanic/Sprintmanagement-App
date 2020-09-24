# Custom Objects and Fields

## Employee__c

Field | Data Type | Description (optional)
------|----------|------------------------
Alias__c | Text(10) |
Email__c | Email |
Name | Text(80) |
First_Name__c | Text(50) |
Is_Active__c | Checkbox |
Last_Name__c | Text(50) |
Mobil__c | Text(50) |
Num_of_Sprints__c | Roll-Up Summary (COUNT Sprint Assignment) | Invisible

## Sprint__c

Field | Data Type | Description (optional)
------|----------|------------------------
Estimated_effort_PD__c | Roll-Up Summary (SUM Ticket) |
Goal__c | Long Text Area(32768) |
Num_of_Tickets__c | Roll-Up Summary (COUNT Ticket) | Count all tickets in the Sprint
Realized_Effort_PD__c | Roll-Up Summary (SUM Ticket) | Summarize all realized effort for one Sprint. It's calculated as follows. This field summarizes values of the field  `Realized_effort_PD__c` on `Ticket` which is a formula field referring to `Realized_effort__c`. The latter is a Roll-Up Summary field (SUM Timesheet Item).
Name | Text(80) | 
Status__c | Picklist | New, Running, Finished
Total_Employees__c | Roll-Up Summary (COUNT Sprint Assignment) |  Invisible


## Ticket__c

Field | Data Type | Description (optional)
------|----------|------------------------
Assigned_to__c | Lookup(Employee) | Lookup Filter: only active
Effort_data_model__c	| Number(16, 2)	|
Effort_deployment__c | Number(16, 2)	|
Effort_documentation__c	| Number(16, 2)	|	
Effort_programming__c |	Number(16, 2)|
Effort_specification__c | Number(16, 2)	|	
Effort_testing__c | Number(16, 2)	|
Estimated_effort__c	| Number(16, 2)	|	
Estimated_effort_PD__c | Formula (Number) | ROUND(Estimated_effort__c / 8, 0)
Estimation_comments__c | Long Text Area(32768)|
Internal_estimate__c | Formula (Number)| Effort_data_model__c + Effort_deployment__c + Effort_documentation__c + Effort_programming__c + Effort_specification__c + Effort_testing__c
Sprint__c | Master-Detail(Sprint)	|	
Status__c | Picklist	| New, Development, Ready for Test, Ready for Deployment, Finished
Name | Text(80)	|
Working_Package_Name__c | Formula (Text)| Sprint__r.Name & " :: " & Name
Realized_effort__c | Roll-Up Summary (SUM Timesheet Item) | Invisible field to summarize all effort for one ticket
Realized_effort_PR__c | Formula (Number) | ROUND(Realized_effort__c/8, 0)

## SprintAssignment__c

An invisible junction object to connect `Sprint__c` and `Employee__c`.

Field | Data Type | Description (optional)
------|----------|------------------------
Email__c | Email | Autopopulated field used in Process `Sprint Assignment` to send an email to Employee when he or she has been assigned to a Sprint
Employee__c | Master-Detail(Employee)	| Lookup Filter: only active
Sprint__c | Master-Detail(Sprint) |
Name | Auto Number |
Unique_External_ID__c | Text(255) (External ID) (Unique Case Sensitive) | Used in workflow rule `Sprint Assignment Unique ID` to prevent duplicates in Sprint Assignments

## Timesheet_Item__c

Die geleistete Arbeitszeit für ein `Ticket` wird durch täglich zu erfassende `Timesheet Items` dokumentiert. Ein `Timesheet Item` verbindet die Tätigkeit eines Mitarbeiters mit einem Ticket an einem bestimmten Tag mit einem bestimmten Aufwand unter Angabe einer kurzen Beschreibung.

Field | Data Type | Description (optional)
------|----------|------------------------
Day__c | Date |
Description__c | Text(255) |
Effort__c | Number(16, 2)
Employee__c | Master-Detail(Employee) | Lookup Filter: only active
Ticket__c | Master-Detail(Ticket)	
Name | Auto Number | TSI-{0000000000}
