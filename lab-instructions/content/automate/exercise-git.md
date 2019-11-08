---
title: "Exercise: GIT"
weight: 1
---

## Publish your API Contract in a GIT repository

Because ACME adheres to the Infrastructure-as-Code and API-Management-as-Code principles, everything needs to be versioned in a GIT repository.
In this exercise, you will create a GIT repository and publish your API contract.

- Go to your [favourite GIT provider]({{< param github_url >}}/new)
- Create a repository named `petstore-api`
- **Hint:** You can initialize it with a README and a license file when proposed by your GIT provider
- Open the [APICurio Studio]({{< param apicurio_studio_url >}}/apis)
- Open your **Petstore** API
- Click the **three dots button** and select **Publish...**
- Click your favourite GIT provider's icon
- Select your login in the **Organization** dropdown list
- Select `petstore-api` in the **Repository** dropdown list
- In the **Resource** field, type `openapi.yaml`
- Fill-in the commit message with something relevant
- Click **Publish API**

Now that you published your API Contract in a GIT repository, we can instruct Microcks to monitor it and reload the new API Contract in case it has been updated.

- Go back to your [favourite GIT provider]({{< param github_url >}})
- Navigate to your repository named **petstore-api**
- Open the **openapi.yaml** file
- Click the **raw** button
- Copy the current URL of your web browser, you will need it in a few moments.
- Open the [Microcks UI]({{< param microcks_url >}})
- Click **Importers** in the left-side menu
- Click the **+ Create** button on the right side of the screen
- Fill-in the **Name** with something like `Petstore API <your login>`
- Fill-in the **Repository URL** with the URL you copied previously
- Click **Next >**
- Enable the **Ignore certificate validity when accessing repository** checkbox
- Click **Next >**
- Next to your importer, click the orange rectangle named **Services**
- Click the service name to open the imported service

Now, each time you publish a new version of the API Contract in your GIT repository, the updated version will appear automatically in Microcks.
