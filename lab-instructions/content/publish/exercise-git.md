---
title: "Exercise: GIT"
weight: 1
---

## Publish your API Contract in a GIT repository

Because ACME adheres to the Infrastructure-as-Code and API-Management-as-Code principles, everything needs to be versioned in a GIT repository.
In this exercise, you will create a GIT repository and publish your API contract.

- Go to your [favourite GIT provider]({{< param github_url >}})
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
