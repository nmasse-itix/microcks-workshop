---
title: "Exercise 2"
weight: 2
---

## Update the API Contract to extend the test coverage

In the previous exercise, ACME discovered its API implementation is not conform to the API contract, this will require some more refinement from the development team.
But ACME also discovered **one missing case** that prevent Microcks from properly asserting the conformity of the API implementation.

In this exercise, you will update the API contract to add examples to the **DELETE /pets/{id}** method.

- Open the [APICurio Studio]({{< param apicurio_studio_url >}}/apis)
- Open your **Petstore** API
- Click **Edit API**
- Start by changing the version number of your API to **1.2.0**
- In the left pane, open the **/pets/{id}** path
- Click **DELETE**
- Scroll down to the **Path parameters** section
- Click **Override**
- Add an example **that you will name "dummy"**
- Set this example's value to `0`
- Scroll down to the **Responses** section
- Add an example **that you will name "dummy"**
- Fill-in this example with:

```json
{"id":0,"name":"Dummy","tag":"dumb"}
```

- In the breadcrumb, click your **Petstore** API
- Scroll down and click **Update Mock in Microcks** > **Mock API** > **OK**
- Click **View in Microcks**
- Unfold the **DELETE /pets/{id}** operation
- **Question:** can you see the examples you defined in Apicurio?

**To complete your understanding**, explain:

- Why we defined an example named "dummy" instead of a proper one such as "zaza"?
- What would be the appropriate setup in a real life scenario?
