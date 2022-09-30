# Message Center to Teams

## Prerequisites

- Service Account
  - G-1
  - Power Automate Per User Plan
- Azure App Registration
  - Graph API

## Steps

1. Create a Registered Application in Azure AD
2. Sign into Azure and connect to the Azure AD tenant
  1. Then follow these steps:
  2. On the left menu, select App registrations.
  3. Click + New Registration.
  4. Screenshot of registering an application in Azure Active Directory
  5. Under Name, enter a unique application name.
  6. Under Supported account types, select Accounts in this organizational directory only.
  7. Click Register.
3. Create a Client Secret for the Registered App
  1. Select the newly created app from the list of App Registrations (if not already visible).
  2. Select Certificates & secrets from the left menu.
  3. Click + New Client Secret.
  4. Provide a Description and appropriate Expiry. If you select 1 or 2 years, the directory credential must be refreshed with a new client secret on the anniversary of its creation.
  5. Click Add.
4. Azure AD copy client secret screenshot
  1. Copy the client secret and store it in a safe place. It is required when for the power automate to run
  2. This is the only time this client secret value is displayed.
5. Azure add api permission to ServiceMessage.Read.All
  1. Select Microsoft Graph, Application Permissions
  2. Search for "ServiceMessage.Read.All"
  3. Select and Click Add permissions.
6. Azure grant admin consent for user and group ServiceMessage.Read.All
  1. Click Grant Admin Consent for \<directory name\> to give consent to the app to have those permissions you just added.
  2. Click Yes to confirm.
7. Your registered app is now created, has a client secret, and has API permissions assigned, select Overview from the left menu and copy the Application (client) ID and the Directory (tenant) ID. Store these in a safe place as these are required to populate the power automate variables
8. Import the power automate
9. Update the Variable with your save values
  1. Tenant ID – Tenant ID
  2. appID - Application ID
  3. theTextSecret – App Secret
