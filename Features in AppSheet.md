# Roles
## Admin Role
Users with "Admin" role have access to all the options other roles have and more.

### Check if you have Admin role
- Method 1: Check in the "Employees" view.
- Method 2: Check if you have the "Admin View" option in the menu.

### Roles / Statuses / Types
- Admin can create, delete Roles, Statuses and Types
  + Default Roles: **Specialist**, Admin, Human Resources, Project Management.
  + Default Statuses: **Active**, Inactive.
  + Default Types: **Full-time**, Part-time, Contractor.
  + **Limit**: You can edit the existing roles/statuses/types, however you can only do it directly on the Google Sheets. And all the employees who use that role have to be edited to get the new role manually in the app interface.
  + You can't create new roles / statuses / types with the same name as existing ones.

- Users assigned with new roles / statuses / types will have their roles automatically changed back to Default value when the new roles / statuses / types are deleted.

### Duplicate Email Check
- Admin can add new emails (users) to the database. However, it is disallowed to have email addresses that already exist in the system. There will be push notification on Android/iOS devices warning about the duplicate emails. 
- Auto-delete duplicate emails from the database.

### Auto-assign and auto-remove Direct Reports of existing users.
- When a new user have a valid value of "Direct Manager" or change their "Direct Manager". The existing Manager will receive an email notification of their new "Direct Reports".
- The managers' data will be updated with the new "Direct Reports" information. 
- When the user is deleted, he will be removed from the Manager's "Direct Reports" list. The existing Manager will receive an email about the removal. 
- **Limit**: Employees who has been edited with a new "Direct Manager" value will automatically update their new managers' information. However, their old managers will still have "Direct Reports" not up-to-date. 

## Human Resources Role
- Users with "Human Resources" role can edit the employees' information (except Role which is only editable by Admins).

## Project Management Role
- Users with "Project Management" role have access to certain Jobs' statuses that are not available to a common user.
  - At certain stages of the job, only Project Managers can change the status of the job. 
- They can create new Projects to manage smaller Jobs. 
  - Projects can be deactivated, which renders all Jobs under that to be removed from the Ongoing Workflow. 
- They can create new Jobs and assign them to users.
  - These users can also edit more of the Jobs' information after creation. 
  - Jobs with "Parent Project State" as "Inactive" can't have their statuses changed. Their information can't be changed. They need to have their parent Projects activated again. 


## Profile Images
- Default Profiles Image is automatically set to be "appsheet/Employees-767296478/Images/default.png" if no image is provided.

![Default Profile Image](./default.png)
- Profiles Images are saved in "appsheet/Employees-767296478/Images/".
- Images are automatically resized despite their large sizes.
- When a user is deleted, the profile image is also removed from the database. 
- **Limit**: There is currently no method to name the image files with whatever names you want.

# Jobs
- Overdue jobs have their names colored red. 

## Calendar
- Jobs in Month Tab are color-coded according to their respective parent projects.
