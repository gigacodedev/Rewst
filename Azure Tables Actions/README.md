# ImmyBot Storage Monitor

## What integrations are required?

- ImmyBot
- ConnectWise Manage

## What does this workflow do?

This workflow will get all ImmyBot devices, query their last reported volume storage metrics, create a list of 
devices that need attention at each client the workflow runs under, and then creates a ConnectWise Manage ticket to 
alert on any devices with a volume that has less than 15% space left

## How do I use this workflow?

### Task Parameters

The "Board ID" and "Status ID" must be changed to match your manage instance. For example, at our MSP these tickets 
are generated on a NOC board for emergent issues that require technician intervention with a "Ready to Dispatch" 
status

### Triggers

There are two triggers, "DEV" and "Every 48 Hours". DEV is a simple webhook trigger, and contains the required 
integration override to test the workflow manually within a sub-organization's context. The Prod trigger will run 
on a 48 hour interval, providing an automated bi-daily sync. The schedule can be edited in this Prod 
workflow if needed, along with the sub-organizations allowed to run (default is all)
