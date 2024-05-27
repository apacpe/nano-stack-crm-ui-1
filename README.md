# nano-stack-crm-ui-1
# Nano Stack Developer Training - CRM UI Extensions
The following are instructions to create a simple CRM UI card and deploy it to HubSpot. The CRM UI card will be built with React and Node.js. 

## Pre-requisites
You will need the following installed on your local machine:
1. [version 20 or higher of NodeJS](https://nodejs.org/)
2. Code editor program such as [Sublime](https://www.sublimetext.com/download), [Atom](https://atom.io/). If you install [Visual Studio Code](https://code.visualstudio.com/download), it comes with an in-built terminal.
3. Terminal program such as [Git Bash](https://gitforwindows.org/), [Hyper](https://hyper.is/) 

You will need to 
1. Check that your portal is on the [CRM Development Tools beta](https://developers.hubspot.com/docs/platform/crm-development-tools-overview#:~:text=If%20you%27re%20not%20currently%20enrolled%20in%20the%20CRM%20development%20tools%20beta%2C%20you%20can%20join%20directly%20form%20your%20HubSpot%20account%3A)

## Deploy a template CRM UI extension to HubSpot
### Install and connect the HubSpot CLI
1. In your local machine, create a directory and change your active directory to it
```
mkdir nano-stack-crm-ui
cd nano-stack-crm-ui
```
2. Install the HubSpot CLI using `npm install -g @hubspot/cli@latest`
3. Connect to your HubSpot portal with `hs init`

4. Follow the prompts to create a personal access key in your web browser. Please check the options under "Sandboxes" and "Serverless Functions"

4. Copy and paste the personal access key into your terminal to authorize the CLI on your local machine to interact with your HubSpot account.


### Create a project and upload a template 

1. Create a project in your portal with `hs project create` then follow the prompts to name your project and save it in a sub-folder

2. Select the `CRM getting started project` template

3. Change your active directory and load the dependencies required to start local development server.
```
cd <your sub-folder name>
npm install
```
4. Run `hs project dev` in this sub-folder and choose to create and deploy to a sandbox or to your main account.
```
If you run into an error, just repeat step 4 and choose the newly created sandbox
```
6. Upload your files to the project with `hs project upload --account=[your account id]` 

7. Click on the link in your terminal response to open the project created in the sandbox/prod portal

8. In your HS portal, go to Contacts Settings and add the CRM UI card to the middle column of your contact records. Check that you're able to see the "Example card" appear on any contact record. 
```
Type some text into the input field and click on "Click Me!"
```
### Project directory structure
Your final project directory should have the following structure:
```
/nano-stack-crm-ui
    |__ /src            
         |__ app
              |__ app.functions
                   |__ serverless.json
                   |__ example-function.js
              |__ extensions
                   |__ example-card.json
                   |__ Example.jsx
                   |__ /node_modules
    |__ readme.md
    |__ package.json
    |__ package-lock.json

```
Review the contents of example-card.json, Example.jsx, serverless.json and example-function.js in a code editor program and note how the files are connected.

### Deploy changes to HubSpot

1. Open the Example.jsx file in the app/extensions folder, in a code editor program and edit the HTML
2. Upload your updated files with `hs project upload --account=[your account name]`
3. Review the changes on your CRM 
