# Azure Tables Actions

## What integrations are required?

- Core

## What does this workflow do?

This workflow will acquire a valid OAUTH2.0 client credentials token, store it along with an expiration value in Rewst's org variables as a secret, then allow for GET and INSERT actions on an Azure Table

## How do I use this workflow?

### Inputs

This workflow has several inputs, and all are required besides the token org variable name. In order to acquire a valid OAUTH2.0 access token, you will need an Entra App Registration that has been granted access to your storage account with permissions to read and edit tables. The tenant ID, Client ID, and Client Secret must be entered to the input variables. Additonally, you will need to know the Row and Partition keys for the data you want to insert or get. If inserting data, the key can be inputted in the `dataName` input, and the value inputted to the `dataValue` input

### Outputs

If data is found, the workflow will output it in a `tableData` output variable. If errors are found and caught, they will be populated in the `errorCollector` output variable

### Triggers

This is designed to be a subworkflow, and thus has no triggers. If you wish to test this workflow, you may want to consider making an "Always Pass" trigger for development