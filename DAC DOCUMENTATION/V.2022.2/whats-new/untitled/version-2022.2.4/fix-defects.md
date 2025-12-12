# Fix Defects

## Fix Defect

| Activity ID | Description                                                                                                                                                                                                                                                                                | Solution                                                                                                                                                     |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| D4C-8493    | The normal User who logged into the web application with basic users privileges can be escalated into Administrative user by tempering the parameter "Admin" as "True" in application request. This will allow the user to access the administration section and can perform admin action. | Now the normal user accessing the web application with privileges basic user cannot be promoted to administrator by changing the parameter "admin" as "tru". |

