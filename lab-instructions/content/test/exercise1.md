---
title: "Exercise: run the test suite"
weight: 1
---

## Run an integration test suite for the ACME Petstore API!

The ACME Petstore has implemented the ACME Petstore API and is about to deploy it into production.
But ACME is unsure about the conformity of its implementation in regards to the API contract.
**Can you help them check if their API matches the API contract?**

The ACME Petstore API implementation has been deployed here:

```raw
{{< param petstore_api >}}
```

- Open the [APICurio Studio]({{< param apicurio_studio_url >}}/apis)
- Open your **Petstore** API
- Scroll down and click **View in Microcks**
- In the **Microcks UI**, click **+ New Test**
- Fill-in the **Test Endpoint** with `{{< param petstore_api >}}`
- Change the **Runner** to **OPEN API SCHEMA**
- Click **+ Launch test!**
- Wait for the test to complete and click **Full results**
- **Question:** How many tests passed? How many failed?
- **Question:** Can you explain why those tests failed?

**To complete your understanding**, explain:

- which changes would be required in the API contract?
- which changes would be required in the API implementation?
