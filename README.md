# AzureEntraBiceps
My Azure/Enra bicep templates.

## subscription_budget.bicep
Used to create a monthly forecasted budget which sends an alert if the forecast is predicted to be over 100% to contactemail.

Example
```Powershell  
New-AzSubscriptionDeployment -TemplateFile .\subscription_budget.bicep -Location 'West Europe' -subscriptionname "mysubscriptioname" -tenant "mytenantdisplayname" -amount 100 -contactEmails "someone@contoso.com"
```

## Parameters

| Parameter | Type | Required | Default Value | Description |
|-----------|------|----------|---------------|-------------|
| tenant | string | Yes | - | Name of Tenant |
| subscriptionName | string | Yes | - | Name of Azure subscription |
| budgetName | string | No | `{tenant} {subscriptionName} monthly` | Name of the Budget. It should be unique within a resource group |
| amount | int | No | 1000 | The total amount of cost or usage to track with the budget |
| startDate | string | No | First day of next month | The start date must be first of the month in YYYY-MM-DD format |
| Threshold | int | No | 100 | Threshold value associated with a notification (percent, between 0.01 and 1000) |
| contactEmails | array | Yes | - | The list of email addresses to send the budget notification to when the threshold is exceeded |  
