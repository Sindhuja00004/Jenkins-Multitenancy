Multi-Tenancy in Jenkins
We can onboard multiple customer users to Jenkins using Role-based Authorization Strategy Plugin. The Role Strategy plugin is meant to add a new role-based mechanism to manage users' permissions.  
Supported Features: 
•	Creating global roles, such as admin, job creator, anonymous, etc., allowing to set Overall,  
Agent, Job, Run, View and SCM permissions on a global basis. 
•	Creating item roles, allowing to set item specific permissions (e.g Job, Run or Credentials) on Jobs, Pipelines and Folders. 
•	Assigning these roles to users and user groups 
 
Folder Plugin: This plugin allows users to create "folders" to organize jobs. 
 
 
Follow the below steps to onboard the user, 
 
•	Navigate to Manage Jenkins > Manage and Assign Roles, create Global Role under manage roles, below example shows tenant1 and tenant2 are the roles created and assigned overall read permission. 
 
  
 
 
•	Create Item role with the pattern which applies to the jobs/folder, below example shows tenant1 and tenant2 are item toles with the pattern tenant1.* and tanent2.* which means if any jobs/folder created with prefix tenant1 belongs tenant1 item role. Provide the permissions to item roles which is required, later will map this role to user. 
 
 

•	If you click on the tenant1.* pattern, shows the matching items which is going to apply this role. 
  
 
 
•	After completing the role creation go to Assign Roles, add the users to Global roles and assign the role to user. 
                
 
 
•	Add the user to Item roles and assign the role to user. This ensures specific user will access the pattern which is created under mange role. Now, user can create job and build the jobs. 

 
  

 
•	We recommend using folder plugin create folder and create pattern which applies to the folder, this approach eliminate the dependency of prefix which is followed to create the jobs with the pattern.  
 
•	We will map the workspace ID of octane to Jenkins user to ensure specific user can only setup their respective jobs in the VE. 


  

