---
title: "Exercise"
weight: 1
---

## Improve the API contract of the ACME Petstore API!

ACME found their first customers and they gave it feedback: a method is required to **update a pet**.
Let's add this method!

Oh, there is a last minute requirement from those customers: in the mock, they would like to be able to update the pet *Zaza* to *Tata*.

- Open the [APICurio Studio]({{< param apicurio_studio_url >}}/apis)
- Open your **Petstore** API
- Click **Edit API**
- Start by changing the version number of your API to **1.1.0**
- In the left pane, open the **/pets/{id}** path
- Click **PUT** > **Add Operation**
- Set the **Operation ID** to `updatePet`
- Fill-in a **Summary** and a **Description**
- Scroll down to the **Path parameters** section
- Click **Override**
- Add an example **that you will name "zaza"**
- Fill-in this example with Zaza's id
- Scroll down to the **Request body** section
- Set the request body to **Required**
- Add a **media type**
- Leave **application/json** as the default **media type** and click **Add**
- Set the type to **Pet**
- Add an example **that you will name "zaza"**
- Fill-in this example with the updated "Zaza" pet

```json
{"id":1,"name":"Tata","tag":"cat"}
```

- Scroll down to the **Responses** section
- Add a **response**
- Select **200 OK** and click **Add**
- Fill-in the description
- Add a **media type**
- Leave **application/json** as the default **media type** and click **Add**
- Set the type to **Pet**
- Add an example **that you will name "zaza"**
- Fill-in this example with the updated "Zaza" pet

```json
{"id":1,"name":"Tata","tag":"cat"}
```

- In the breadcrumb, click your **Petstore** API
- Scroll down and click **Update Mock in Microcks** > **Mock API** > **OK**
- Click **View in Microcks**
- Unfold the **PUT /pets/{id}** operation
- **Question:** can you see the examples you defined in Apicurio?
- If you have access to a command line with curl installed, you can test your new mock: 
  - Copy the mock URL given by Microcks
  - Execute the following command:

```sh
curl -XPUT -H "Content-Type: application/json" -d '{"id":1,"name":"Tata","tag":"cat"}' https://replace.me.by/mock/url
```

**To complete your understanding**, explain:

- why we asked you to name all your examples **zaza**?
- what would be required to mock the PUT operation to rename **Maki** (pet number 3) to **Sushi**?
