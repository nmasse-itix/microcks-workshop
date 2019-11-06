---
title: "Exercise"
weight: 1
---

## Craft the API contract of the ACME Petstore API!

The ACME petstore is about to adopt APIs **in order to expose their catalog of pets** to the outside world. Help them design an API contract!

- Open the [APICurio Studio]({{< param apicurio_studio_url >}}/apis/create)
- Register if you are a newcomer or login if you already have an account
- Give a name to your API (**Please add your login to the API name so that it is unique amongst all participants**)
- Invent a nice description for your API
- Leave the **type** to **Open API 3.0.2**
- Select the **Petstore Example** as starting **Template**
- Click **Create API**
- Click **Edit API**

The existing template is quite good but we will make a small change for the sake of exploring Apicurio.

- Click the **/pets/{id}** path
- Scroll down to the **Operations** section
- Click the **DELETE** operation
- Scroll down to the **Responses** section
- Click the little trash icon on the right side of the screen to remove the existing responses
- Click **Add a response**
- Leave **200 OK** as the default response
- Fill-in a description
- Click **Add a media type**, leave **application/json** as the default media type and click **Add**
- Change the return type to **Pet**

Congratulations! You just designed your first API Contract in a graphical way!

**To complete your understanding**, explain which method is missing in the Petstore API to have a proper CRUD API?
