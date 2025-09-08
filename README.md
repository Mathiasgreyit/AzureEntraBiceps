# AzureEntraBiceps
My Azure/Enra bicep templates.

## subscription_budget.bicep
Used to create a monthly forecasted budget which sends an alert if the forecast is predicted to be over 100% to contactemail.

Example  
New-AzSubscriptionDeployment -TemplateFile .\subscription_budget.bicep -Location 'West Europe' -subscriptionname "mysubscriptioname" -customer "mytenantdisplayname" -amount 100 -contactEmails "someone@contoso.com"
