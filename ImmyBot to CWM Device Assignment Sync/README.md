# ImmyBot to ConnectWise Manage Device Assignment Sync

## What integrations are required?

- ImmyBot
- ConnectWise Manage

## What does this workflow do?

This workflow will list all ImmyBot Devices, filter the devices with an Immy user assigned, then assign the matching ConnectWise Manage contact to the corresponding CWM configuration.

## How do I use this workflow?

### Triggers

There are two triggers, "DEV" and "Prod - Cron Schedule". DEV is a simple webhook trigger, and contains the required integration override to test the workflow manually within a sub-organization's context. The Prod trigger is Cron scheduled to run daily at 00:00UTC, providing an automated daily sync. The schedule can be edited in this Prod workflow if needed, along with the sub-organizations allowed to run (default is all)

> [!NOTE]  
> Need help with your Cron syntax? Check out [Crontab.Guru](https://crontab.guru)
