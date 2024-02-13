# Send SMTP2Go Email

## What integrations are required?

- Core

## What does this workflow do?

This subworkflow will craft and send the required API call to SMTP2Go to send an email

## How do I use this workflow?

### Inputs

- to
    - A list of addresses to send the email to
    - Must be a list object, even with only one email
- sender
    - Email address to display as the sender. Domain must be validated in SMTP2Go
- subject
    - Email subject
- html_body
    - Body of email formatted as HTML
- api_key
    - API key for SMTP2Go account
    - **IMPORTANT**: To prevent leaking the API key in results or workflow, it is recommended you save it as a secret org variable at your top level organization accessible to child orgs. When the subworkflow is used, be sure to redact this input variable in the security tab. The subworkflow already is set to redact its body and auth details.

### Outputs

None

### Triggers

This is designed to be a subworkflow, and thus has no triggers. If you wish to test this workflow, you may want to consider making an "Always Pass" trigger for development