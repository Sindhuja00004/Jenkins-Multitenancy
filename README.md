                                                    MULTITENANCY IN JENKINS

We can onboard multiple customer users to Jenkins using Role-based Authorization Strategy Plugin. The Role Strategy plugin is meant to add a new role-based mechanism to manage users' permissions. 

Supported Features: 

•	Creating global roles, such as admin, job creator, anonymous, etc., allowing to set Overall,  
Agent, Job, Run, View and SCM permissions on a global basis. 

•	Creating item roles, allowing to set item specific permissions (e.g Job, Run or Credentials) on Jobs, Pipelines and Folders. 

•	Assigning these roles to users and user groups 

Folder Plugin: This plugin allows users to create "folders" to organize jobs. 
 
 Follow the below steps to onboard the user, 
 
•	Navigate to Manage Jenkins > Manage and Assign Roles, create Global Role under manage roles, below example shows tenant1 and tenant2 are the roles created and assigned overall read permission. 
 
![image](https://user-images.githubusercontent.com/95271479/217833711-d58d232f-a164-43ef-821e-bd428454ae2d.png)

•	Create Item role with the pattern which applies to the jobs/folder, below example shows tenant1 and tenant2 are item toles with the pattern tenant1.* and tanent2.* which means if any jobs/folder created with prefix tenant1 belongs tenant1 item role. Provide the permissions to item roles which is required, later will map this role to user. 
 
![image](https://user-images.githubusercontent.com/95271479/217833987-c2546365-bb74-461c-a88b-2d74045a7764.png)

•	If you click on the tenant1.* pattern, shows the matching items which is going to apply this role. 

![image](https://user-images.githubusercontent.com/95271479/217834191-ec5a64f7-5554-4d0e-b4cb-e3c7770b4da5.png)

•	After completing the role creation go to Assign Roles, add the users to Global roles and assign the role to user. 

![image](https://user-images.githubusercontent.com/95271479/217834446-a45ac9d1-50be-45be-a821-ba4e5ded4540.png)

•	Add the user to Item roles and assign the role to user. This ensures specific user will access the pattern which is created under mange role. Now, user can create job and build the jobs. 

![image](https://user-images.githubusercontent.com/95271479/217834622-b0288b16-a2dd-4920-a1fa-1ce39bf60d4a.png)   ![image](https://user-images.githubusercontent.com/95271479/218018847-c5aa43da-6fe1-4b82-9c3a-43454aef0b9a.png)


•	We recommend using folder plugin create folder and create pattern which applies to the folder, this approach eliminate the dependency of prefix which is followed to create the jobs with the pattern.  
 
•	We will map the workspace ID of octane to Jenkins user to ensure specific user can only setup their respective jobs in the VE. 

![image](https://user-images.githubusercontent.com/95271479/217834968-1ee1242e-79df-454b-86b5-15bb515bfa60.png)



 
