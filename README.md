# MeldRx Demo App - Blank (React)

## Getting Started

### Preqrequisites
- NodeJs

### MeldRx Setup - Developer Account
- Go to `https://app.stg.meldrx.com` and create a _Developer Account_
    - Choose any username/password you want
- Go to `https://developer.stg.meldrx.com` and login
    - If you get redirected, just go back to `https://developer.stg.meldrx.com`

### MeldRx Setup - App Creation
- Go to `Command Center > My Apps`
- Create a new app
    - Name: `My Provider App`
    - App User Type: `Provider`
    - Client Type: `Public`
    - Scopes: Open it up and select all
        - If you get an error when you save your app, scroll to the bottom of scopes and remove any `user/` and `system/` scopes
    - Redirect Urls:
        - `https://localhost:3000/app`
        - `http://localhost:3000/app`
        - `http://localhost:8100/authentication/login-callback`
    - Post-Logout Urls:
        - `http://localhost:8100/logout` (not used)
- Save your app and click it again to edit it
- Go to Linked Apps and create a new Linked App
    - FHIR API Provider: Type "Epic" and select one of them. Make a note of specifically which one you chose
    - App User Type: `Provider`
    - Client Id: {Use the client Id obtained from Eric}
    - Scopes: Open it up and select all

### MeldRx Setup - Workspace Creation
- Go to `Command Center > My Workspaces`
- Create a new Workspace (please enter everything in this exact order because there is a visual bug)
    - Name: `Epic Sandbox`
    - Description: `Epic Sandbox`
    - Connect to External FHIR Server: `checked`
    - FHIR URL: `https://fhir.epic.com/interconnect-fhir-oauth/api/FHIR/R4`
        - Click Validate
    - FHIR API Provider: Select the exact same one as when you created your linked app
### App Setup/Installation
- Run `npm install`

### App Configuration
- Open `config/config.ts`
- Replace the `clientId` with the Client Id (aka "MeldRx App Id") of your **MeldRx App** (Get this from the "My Apps" page)
- Replace the `workspaceId` with the Workspace Id of your workspace (it's the GUID at the end of the endpoint)
### Run the App
- `npm run dev`
