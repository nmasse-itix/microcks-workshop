---
title: "Exercise: re-run the tests"
weight: 3
---

## Re-run the test suite

In the previous exercise, you updated the API contract to add examples to the **DELETE /pets/{id}** method so that Microcks can assert the whole Petstore API.
In the meantime, the development team fixed the **POST /pets** operation to return **200 OK** as required by the API Contract.

The updated ACME Petstore API implementation has been deployed here:

```raw
{{< param petstore_api_fixed >}}
```

- Open the [APICurio Studio]({{< param apicurio_studio_url >}}/apis)
- Open your **Petstore** API
- Scroll down and click **View in Microcks**
- In the **Microcks UI**, click **+ New Test**
- Fill-in the **Test Endpoint** with `{{< param petstore_api_fixed >}}`
- Change the **Runner** to **OPEN API SCHEMA**
- Click **+ Launch test!**
- Wait for the test to complete and click **Full results**
- **Question:** Did all the tests passed?
