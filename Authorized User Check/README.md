# Authorized User Check

## Workflows Included

- Set Authorized Users: Add selected authorized users to org variables
- Get Customer Graph Licensed Users: Get users with licenses from Graph for option gen on form
- Check if Authorized: Verify submitting user is in Authorized Users org var
- Get MSP Users (Optional): Adds all users in your internal org to approved submitter lists

## Forms Included

- Set Authorized Form User

## What integrations are required?

- Core
- ConnectWise Manage (For alerts on new Authorized User additions)

## What does this workflow do?

This workflow allows you to authorize users who are submitting a form. To check in a parent workflow, such as 
employee onboarding, add "Check if Authorized" as a subworkflow. This will output the variable "Authorized" which is 
a boolean. To set authorized users, the "Set Authorized Users" workflows and forms will allow easy addition of new 
authorized users per tenant. Lastly, if all of your internal users should be authorized to submit forms on a 
customer's behalf, the "Get MSP Users" workflow will periodically update an "MSPUsers" org variable which is then 
checked by default in the "Check if Authorized" flow

## How do I use this workflow?

### Task Parameters

- Set Authorized Users
  - CreateAlertTicket Task
    - Board and Status IDs must be updated to match the desired board and status in your Manage instance
- Get MSP Users
  - rewst_bulk_upsert_organization_variables Task
    - Organization ID must be changed to your Rewst organization ID


### Triggers

- Set Authorized Users
  - Form
    - Form to fill to designate authorized users for onboard and offboards. This includes a dynamic dropdown with 
all licensed 365 users in the tenant
- Get MSP Users
  - A time interval or cron trigger should be created to support ongoing sync. This is not included as the interval 
should be up to the importing MSP. Internally, we check daily. But this can be whatever interval you'd like.
