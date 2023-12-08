# Prerequisites

## Service Account
- G-1
- Power Automate Per User Plan

## Azure App Registration
- Graph API

# Steps

1. **Create a Registered Application in Azure AD**

    a. Sign into Azure and connect to the Azure AD tenant.
    
    b. On the left menu, select App registrations.
    
    c. Click `+ New Registration`.
    
    d. ![Screenshot of registering an application in Azure Active Directory]([link-to-screenshot](https://github.com/MSPFE2019/MessageCenter-to-Teams/raw/905b578559f3a1191afe8df92feb12f4ec4b443f/Screenshot%202022-09-29%20225107.png)
    
    e. Under Name, enter a unique application name.
    
    f. Under Supported account types, select Accounts in this organizational directory only.
    
    g. Click `Register`.

2. **Create a Client Secret for the Registered App**

    a. Select the newly created app from the list of App Registrations (if not already visible).
    
    b. Select Certificates & secrets from the left menu.
    
    c. Click `+ New Client Secret`.
    
    d. Provide a Description and appropriate Expiry. If you select 1 or 2 years, the directory credential must be refreshed with a new client secret on the anniversary of its creation.
    
    e. Click `Add`.

3. **Copy the Azure AD Client Secret**

    a. Copy the client secret and store it in a safe place. It is required when for the Power Automate to run.
    
    b. This is the only time this client secret value is displayed.

4. **Azure AD - Add API Permission to ServiceMessage.Read.All**

    a. Select Microsoft Graph, Application Permissions.
    
    b. Search for “ServiceMessage.Read.All”.
    
    c. Select and Click `Add permissions`.

5. **Azure AD - Grant Admin Consent for User and Group ServiceMessage.Read.All**

    a. Click `Grant Admin Consent` to give consent to the app to have those permissions you just added.
    
    b. Click `Yes` to confirm.

6. **Retrieve Application and Directory IDs**

    a. Your registered app is now created, has a client secret, and has API permissions assigned. Select `Overview` from the left menu and copy the `Application (client) ID` and the `Directory (tenant) ID`. Store these in a safe place as these are required to populate the Power Automate variables.

7. **Import the Solution in the Appropriate Environment in Your Tenant**

8. **Update the Environment Variables with Your Saved Values During the Import of Solution**

    a. `MC2TeamsTenant ID` – Tenant ID
    
    b. `MC2TeamsClientID` - Application ID
    
    c. `MC2TeamsSecret` – App Secret

9. After import, open the flow and change the Teams settings as specified for the Team and Channel.
