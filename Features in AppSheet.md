# Employees
## Admin Roles
### Roles / Statuses / Types
- Admin can create, delete new Roles, Statuses and Type_Ref
  + Default Roles: **Specialist**, Admin
  + Default Statuses: **Active**, Inactive
  + Default Types: **Full-time**, Part-time, Contractor
  + You can edit the existing role/status/type, however you can only do it directly on the Spreadsheet. And all the employees who use that role have to be edited to get the new role manually.
  + You can't create new roles / statuses / types with the same existing name.

- Users assigned with new roles / statuses / types will have their roles automatically changed back to Default value when the new roles / statuses / types are deleted.

### Duplicate Email Check
- Admin can add new emails to the system. However, it is disallowed to have email addresses that already exist in the system. There will be push notification on Android/iOS devices about the duplicate emails. 

## Profile Images
- Default Profiles Images automatically set at "appsheet/Employees-767296478/Images/default.png"
- Profiles Images are saved in "appsheet/Employees-767296478/Images/".
- Images are automatically resized despite their large sizes.
- When a user is deleted, the profile image is also removed from the system. 

# Versions
- 1.000022: Profile Images feature is completed.
- 1.000054: Role_Ref, Status_Ref and Type_Ref
