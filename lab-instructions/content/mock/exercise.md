---
title: "Exercise"
weight: 1
---

## Expose a Mock of the ACME Petstore API!

As the ACME Petstore API matures, the sales representative of the ACME Petstore already found his first customers. In this exercise, you will have to **expose a mock of the ACME Petstore API** so that future customers can start their implementation ahead and provide feedback early.

- Open the [APICurio Studio]({{< param apicurio_studio_url >}}/apis)
- Open your **Petstore** API
- Select **Mock with Microcks**
- Click **Mock API**
- Click **OK**
- Click **View in Microcks**
- In the **Microcks UI**, unfold the four operations and discover the generated mock URLs
- Copy the URL of the **GET /pets** operation and paste it in a new tab of your web browser
- **Question:** How many pets are there?
- Copy the URL of the **GET /pets/{id}** operation and paste it in a new tab of your web browser
- **Question:** What is the name of the pet you retrieved?
- **Question:** What if you change the numerical id to **2**, **3** or **4** in the mock URL?

**To complete your understanding**, explain:

- how the mock is generated: where do those pets come from?
- what would be needed to add **Tigresse**, **Maki** and **Toufik** as valid responses to the **GET /pets/{id}** operation?
- how the future customers of ACME can use this mock to develop their implementation ahead?
