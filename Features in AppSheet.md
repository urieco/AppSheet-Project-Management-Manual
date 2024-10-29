# Table of Contents
- [Roles](#roles)
  - [Admin Role](#admin-role)
    - [Check if you have Admin Role](#check-if-you-have-admin-role)
    - [Admin View](#admin-view)
    - [Roles / Statuses / Types](#roles--statuses--types)
    - [Duplicate Email Check](#duplicate-email-check)
    - [Auto-assign and auto-remove Direct Reports of existing users](#auto-assign-and-auto-remove-direct-reports-of-existing-users)
    - [Projects / Jobs / Notes](#projects--jobs--notes)
  - [Human Resources Role](#human-resources-role)
  - [Project Management Role](#project-management-role)
  - [Other Roles](#other-roles)
- [Employees](#employees)
  - [Profile Images](#profile-images)
- [Projects](#projects)
- [Jobs](#jobs)
  - [Features](#features)
  - [Workflow](#workflow)
  - [Calendar](#calendar)
- [Notes](#notes)
  - [Attachment Files](#attachment-files)

# Roles
## Admin Role
Users with Admin role have access to all the options other roles have and more.

### Check if you have Admin Role
- Method 1: Check in the "Employees" view.
- Method 2: Check if you have the "Admin View" option in the menu.

### Admin View
- A custom view for users with Admin role to view, add and delete certain built-in values:
  - Employees' Role Ref: "Admin", "Project Management", "Human Resources",etc.
  - Employees' Status Ref: "Active", "Inactive", "On Leave", etc.
  - Employees' Employment Type Ref: "Full-time", "Part-time", "Contractor", etc.
  - Employees Image: A gallery of all submitted employees' profile pictures.
  - Jobs' Status Ref: "New Job", "Awaiting Clarification", "In Production", etc.
  - Jobs' Priority Ref: "Low", "Medium", "High", etc.
- **Limit**: 
  - You can only edit existing Roles / Statuses / Types / ... in the Database sheet. However, it is not recommended as the Employees or Jobs that are affixed with those values will still hold the old value until you manually edit it. 

### Roles / Statuses / Types
- Admin can create, delete Roles, Statuses and Types
  + Default Roles: **Specialist**, Admin, Human Resources, Project Management.
  + Default Statuses: **Active**, Inactive.
  + Default Types: **Full-time**, Part-time, Contractor.
  + You can't create new roles / statuses / types with the same name as existing ones.
  + **Limit**: You can edit the existing roles/statuses/types, however you can only do it directly on the Google Sheets. And all the employees who use that role have to be edited to get the new role manually in the app interface.

- Users assigned with new roles / statuses / types will have their roles automatically changed back to Default value when the new roles / statuses / types are deleted.

### Duplicate Email Check
- Admin can add new emails (users) to the database. However, it is disallowed to have email addresses that already exist in the system. There will be push notification on Android/iOS devices warning about the duplicate emails. 
- Auto-delete duplicate emails from the database.

### Auto-assign and auto-remove Direct Reports of existing users.
- When a new user have a valid value of "Direct Manager" or change their "Direct Manager". The existing Manager will receive an email notification of their new "Direct Reports".
- The managers' data will be updated with the new "Direct Reports" information. 
- When the user is deleted, he will be removed from the Manager's "Direct Reports" list. The existing Manager will receive an email about the removal. 
- **Limit**: Employees who has been edited with a new "Direct Manager" value will automatically update their new managers' information. However, their old managers will still have "Direct Reports" not up-to-date. 

### Projects / Jobs / Notes
- Admin users have full control over adding, modifying and removing Projects / Jobs / Notes which other Roles are restricted to only adding new items.

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

## Other Roles
- Other roles are quite restricted.
- They can edit the certain statuses of the Job.
- They can add new Notes.

# Employees
- You can quickly navigate to the "Projects" that the Employee owns, the Jobs that the Employee is assigned to and the Notes that they have provided for certain Jobs.

## Profile Images
- Default Profiles Image is automatically set to be "appsheet/Employees-767296478/Images/default.png" if no image is provided.

![Default Profile Image](./default.png)
- Profiles Images are saved in "appsheet/Employees-767296478/Images/".
- Images are automatically resized despite their large sizes.
- When a user is deleted, the profile image is also removed from the database. 
- **Limit**: There is currently no method to name the image files with whatever names you want.

# Projects
- Shows a list of Projects.
- New Projects have their "Project Number" set according to the number of Projects in the database. Ex: There are already 12 jobs in the database, new Jobs will start with their "Job Number" at 13. 
- You can quickly navigate to the "Employees" from the "Project Owner" field.
- Projects' detail pages also shows briefly all the jobs that belong to those Projects. 
- Projects can be deactivated by Admin / Project Management role holders. Deactivated projects appear fainter than the rest. All the jobs under those Projects are disallowed from editing / changing status until that Projects are activated again. 

# Jobs
## Features
- New Jobs have their "Job Number" set according to the number of Jobs in the database. Ex: There are already 12 jobs in the database, new Jobs will start with their "Job Number" at 13. 
- Each status has a different symbol for users to quickly identify the status of the Job. 
- Users logging into the app are greeted with "Jobs" View which showcases all Jobs.
- "Ongoing Jobs" view displays 5 tabs:
  - "Ongoing Jobs": displays Jobs that don't have their parent Projects set to "Inactive". Jobs that are not "On-Hold", "Cancelled" or "Completed".
  - "Production": displays Jobs that are "New Job", "In Production" or "Edits Required".
  - "Appraisal": displays Jobs that are "Awaiting Clarification", "To Be Approved", or "Approved".
  - "On-Hold": displays Jobs that are "On-Hold".
  - "Cancelled" or "Completed" Jobs are added to "Archived Jobs". 
- Overdue Jobs have their names colored red. 
- Completed Jobs have their names crossed.
- When a Job is marked "Completed", their "Completed" value is updated to the time the Job is finished.
- You can quickly navigate to the Parent Projects' detail pages and the assigned Employees' detail pages from the Jobs.

## Workflow
- All new Jobs are assigned status "New Job".
- "New Job": Can be changed to:
  - "In Production"
  - "Awaiting Clarification"
  - "On-Hold" (Admin / Project Management) 
  - "Cancelled" (Admin / Project Management)
<br><br>
- "In Production": Can be changed to:
  - "To Be Approved"
  - "Awaiting Clarification"
  - "On-Hold" (Admin / Project Management) 
  - "Cancelled" (Admin / Project Management)
<br><br>
- "To Be Approved": Can only be changed by Admin / Project Management to:
  - "Approved"
  - "Edits Required"
  - "On-Hold"
  - "Cancelled"
<br><br>
- "Edits Required": Can be changed to:
  - "In Production"
  - "To Be Approved"
  - "On-Hold" (Admin / Project Management) 
  - "Cancelled" (Admin / Project Management)
<br><br>
- "Awaiting Clarification": Can be changed to:
  - "In Production"
  - "On-Hold" (Admin / Project Management) 
  - "Cancelled" (Admin / Project Management)
<br><br> 
- "Approved": Can be changed to:
  - "Edits Required" (Admin / Project Management)
  - "Completed"
<br><br>
- "Completed": Can only be changed by Admin / Project Management to:
  - "In Production"
  - "Edits Required"
<br><br>
- "On-Hold" or "Cancelled": Can only be changed by Admin / Project Management to:
  - "In Production"
<br><br><br>

**Limit**: When a new Job Status is added via Admin. The App owner has to reconfigure the workflow manually to fit in the new Status.

## Calendar
- "Upcoming" tab: Shows Jobs that are due in the next 7 days.
- "Overdue" tab: Shows Jobs that are overdue.
- "Month" tab: Shows Due dates of Jobs on a calendar.
  - Jobs in Month Tab are color-coded according to their respective parent projects.

# Notes
- You can quickly navigate to the Job that a Note is attached to and the Employee that authors the note. 
- It also includes "Link" field for adding external links. 

## Attachment Files
- Notes include "File" field for adding attachments.
- When a Note with an attached file is deleted. The file is also deleted from the database.