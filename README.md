# nano-stack-crm-ui-1
# Nano Stack Developer Training - CRM UI Extensions
The following are instructions to create a simple CRM UI card and deploy it to HubSpot. The CRM UI card will be built with React and Node.js. 

## Pre-requisites
Before your first training, you must complete the following:
- Please confirm that your portal is on the [CRM Development Tools beta](https://developers.hubspot.com/docs/platform/crm-development-tools-overview#:~:text=If%20you%27re%20not%20currently%20enrolled%20in%20the%20CRM%20development%20tools%20beta%2C%20you%20can%20join%20directly%20form%20your%20HubSpot%20account%3A)-
- Please install the following on your local machine:
    1. [NodeJS (version 20 or higher)](https://nodejs.org/) 
    2. A code editor program such as
         - [Visual Studio Code](https://code.visualstudio.com/download) (recommended as it comes with an in-built terminal)
         - [Sublime](https://www.sublimetext.com/download), [Atom](https://atom.io/). 
    3. A terminal program such as
        - [Git Bash](https://gitforwindows.org/)
        - [Hyper](https://hyper.is/) 

## Deploy a template CRM UI extension to HubSpot
### Install and connect the HubSpot CLI
1. In your local machine, create a directory using `mkdir nano-stack-crm-ui`

2. After creating a new directory, change your active directory using `cd nano-stack-crm-ui`

3. Install the HubSpot CLI using `npm install -g @hubspot/cli@latest` You should see the installation loading and completed on your terminal.

4. Connect to your HubSpot portal with `hs init`. 

5. Respond to the prompt "Open hubspot.com to copy your personal access key?" with `Y`.This will launch HubSpot in a web browser.

6. Follow the prompts to create a personal access key in your web browser. Please check the options under "Sandboxes" and "Serverless Functions". If you already have a personal access key created in your portal, ensure that "Sandboxes" and "Serverless Functions" are selected scopes.

7. Copy and paste the personal access key into your terminal to authorize the CLI on your local machine to interact with your HubSpot account. Follow the prompts to name the account and set it as default. 

### Create a project and upload a template 

1. Create a project in your portal with `hs project create`, then give your project a short and simple name. 

2. Respond to the prompt "Where should the project be created?" with `.` to create the project in the folder you are currently in. 

3. Respond to the prompt "Choose a project template" with `Select the `CRM getting started project` template`

4. Load the dependencies required to start local development server using `npm install`

5. Run `hs project dev` in this sub-folder and choose to create and deploy to a sandbox or to your main account. If you run into an error, just repeat step 4 and choose the newly created sandbox.

6. Upload your files to the project with `hs project upload --account=[your account id]` 

7. Click on the link in your terminal response to open the project created in the sandbox or prod portal

8. Follow [these steps](https://knowledge.hubspot.com/object-settings/customize-the-middle-column-of-records#edit-the-middle-column-s-layout-and-content) to Customize your CRM display to add the CRM UI card to the middle column of your contact records. When adding the new card to your contact record, the card will be labelled  "Example card". 

9. Navigate to a contact record and check that you're able to see the "Example card". 

10. On the card in the contact record, type some text into the input field and click on "Click Me!"

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

1. Open the Example.jsx file in a code editor program and edit the HTML
2. Upload your updated files with `hs project upload --account=[your account id]`
3. Review the changes on your CRM

---
Refer to [this resource](https://docs.google.com/document/d/158lC7iaTETgKKQVDs4rdOBRZ_9vSUIBIlpByFh0b_4o/edit#heading=h.gzn6elt46xf7) to troubleshoot common errors encountered during this session. 
