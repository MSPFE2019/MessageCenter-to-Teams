# **Message Center to Teams**

![](https://github.com/MSPFE2019/MessageCenter-to-Teams/blob/905b578559f3a1191afe8df92feb12f4ec4b443f/Screenshot%202022-09-29%20225107.png) {align=center}

## Prerequisites

·        Service Account

o  G-1

o  Power Automate Per User Plan

·        Azure App Registration

o   Graph API

## Steps

  [Download Link](https://github.com/MSPFE2019/MessageCenter-to-Teams/blob/ee8b4067cd73f31218957e86da2b4d57e4da3200/GetM365ServiceMessages_20220929213956.zip)

1.      Create a Registered Application in Azure AD

2.      Sign into Azure and connect to the Azure AD tenant

a.      Then follow these steps:

b.      On the left menu, select App registrations.

c.      Click + New Registration.

d.      Screenshot of registering an application in Azure Active Directory

e.      Under Name, enter a unique application name.

f.       Under Supported account types, select Accounts in this organizational directory only.

g.      Click Register.

3.      Create a Client Secret for the Registered App

a.      Select the newly created app from the list of App Registrations (if not already visible).

b.      Select Certificates & secrets from the left menu.

c.      Click + New Client Secret.

d.      Provide a Description and appropriate Expiry. If you select 1 or 2 years, the directory credential must be refreshed with a new client secret on the anniversary of its creation.

e.      Click Add.

4.      Azure AD copy client secret screenshot

a.      Copy the client secret and store it in a safe place. It is required when for the power automate to run

b.      This is the only time this client secret value is displayed.

5.      Azure add api permission to ServiceMessage.Read.All

a.      Select Microsoft Graph, Application Permissions

b.      Search for “ServiceMessage.Read.All”

c.      Select and Click Add permissions.

6.      Azure grant admin consent for user and group ServiceMessage.Read.All

a.      Click Grant Admin Consent for <directory name> to give consent to the app to have those permissions you just added.

b.      Click Yes to confirm.

7.       Your registered app is now  created, has a client secret, and has API permissions assigned, select Overview from the left menu and copy the Application (client) ID and the Directory (tenant) ID. Store these in a safe place as these are required to populate the power automate variables

8.      Import the power automate [Link to File](https://github.com/MSPFE2019/MessageCenter-to-Teams/blob/ee8b4067cd73f31218957e86da2b4d57e4da3200/GetM365ServiceMessages_20220929213956.zip)

9.      Update the Variable with your save values

a.      Tenant ID – Tenant ID

b.      appID - Application ID

c.      theTextSecret – App Secret
