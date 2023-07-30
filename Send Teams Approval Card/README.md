# Send Teams Approval Card

## What integrations are required?

- Rewst Core

## What does this workflow do?

This workflow will intake information on an activity to receive approval, then POST an Adaptive Card with Approve and Deny buttons. Once a button is selected, the workflow will output a boolean with True representing approval, and False represential denial. If using ConnectWise Manage PSA, an additional button to view ticket can be inserted by providing a ticket number and company ID
>[!IMPORTANT]  
>An action must be received before the workflow times out for an output to be provided. The default timeout is 60 minutes. To change this, increase the task timeout on the `WebhookResponse` action. This time may not exceed the default workflow timeout of 8 hours.

## How do I use this workflow?

>[!NOTE]  
>This workflow works best when used as a subworkflow to receive a response before proceeding with other actions, and is designed as such

### Inputs

- `teamsWebhook`
  - Type: Text  
  - Required: Yes  
  - Description: Teams Channel Webhook to send message to
- `header`
  - Type: Text
  - Required: Yes
  - Description: Large header portion of Adaptive Card message
- `message`
  - Type: Text
  - Required: Yes
  - Description: Normal text below header of message
- `factList`  
  - Type: List
  - Required: No
  - Description: List of "facts" to display. This is a list of information containing both a name and value. Number of facts in Adaptive Card will dynamically scale to match number of provided facts in list
  - List Syntax: `[{ "name": "FactHeader", "value": "FactMessage"}]`
- `ticketNumber`
  - Type: Text  
  - Required: No
  - Description: If using ConnectWise Manage PSA, an additional button to view ticket can be inserted by providing a ticket number and company ID
- `manageCompany`
  - Type: Text  
  - Required: No
  - Description: If using ConnectWise Manage PSA, an additional button to view ticket can be inserted by providing a ticket number and company ID.

### Outputs

- `approved`  
  - Type: Boolean
  - Description: `True` indicates an approval was received. `False` indicates a denial was received.

### Triggers

None - Subworkflow
