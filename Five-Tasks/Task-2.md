# Task 2 – Microsoft Entra ID Users, Groups, Tenant, and Guest Users

## Objective

To understand and manage Microsoft Entra ID users, groups, tenants, and guest users in Microsoft Azure.

## Microsoft Entra ID

Microsoft Entra ID is Microsoft's cloud-based identity and access management service. It provides authentication and authorization for users, groups, applications, and other resources.

## Procedure

### 1. Access Microsoft Entra ID

Microsoft Entra ID was opened from the Azure Portal.

The **Microsoft Entra ID** service was selected from the Azure Portal.

### 2. Configure Azure AD Users

Microsoft Entra ID provides options for creating and managing users.

The **Users** section was opened to examine user management options.

The **New user** option was checked for creating an internal Microsoft Entra user.

However, the university-provided account did not have the required administrative permissions to create new users. The **New user** option was therefore unavailable for the account.

This demonstrated that user creation requires appropriate Microsoft Entra administrative permissions.

### 3. Configure Microsoft Entra Groups

The **Groups** section was opened to examine group management.

Microsoft Entra supports different group membership types, including:

- Assigned membership
- Dynamic User membership
- Dynamic Device membership

Assigned groups allow administrators to manually add members.

Dynamic groups automatically add or remove members based on defined membership rules.

The account used for the lab did not have sufficient permissions to create dynamic groups. Therefore, the dynamic group configuration could not be completed using the university account.

### 4. Microsoft Entra Tenant

A Microsoft Entra tenant provides an identity boundary for an organization. It contains users, groups, applications, and other identity-related resources.

The existing university Microsoft Entra tenant was used for this practical exercise.

Creating a separate tenant was not performed because tenant creation requires the appropriate permissions and was not necessary for the remaining Azure practical tasks.

### 5. Manage Microsoft Entra Guest Users

Microsoft Entra ID supports guest users for collaboration with users outside an organization.

Guest users can be invited into an organization's Microsoft Entra tenant and can be assigned appropriate permissions according to organizational requirements.

Guest user management was reviewed as part of the Microsoft Entra ID practical.

## Permission Limitation

The university-provided Azure account did not have the required administrative roles for creating internal users and dynamic groups.

The **User Administrator** role was checked, and the account was not assigned this role.

Therefore, user and dynamic group creation could not be completed with the available permissions.

## Result

Microsoft Entra ID user, group, tenant, and guest-user management concepts were examined.

The available university account was successfully used to access Microsoft Entra ID, but some administrative operations were restricted because the required permissions were not assigned.

## Conclusion

This task demonstrated the basic identity and access management capabilities of Microsoft Entra ID. It also showed the importance of assigning appropriate administrative roles before performing user and group management operations.
