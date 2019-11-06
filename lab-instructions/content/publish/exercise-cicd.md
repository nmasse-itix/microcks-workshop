---
title: "Exercise: CI/CD"
weight: 2
---

## Include the Microcks tests in your CI/CD pipeline

Because ACME adheres to the Infrastructure-as-Code and API-Management-as-Code principles, everything needs to be versioned in a GIT repository and deployed automatically without human intervention.
ACME would like to trigger the Microcks tests from their CI/CD pipeline, based on GitHub Actions or Tekton.

In this exercise, you will trigger a Microcks test from the CLI (we can imagine that someone at ACME would add this CLI to the CI/CD pipeline...).

- Have a look at the [microcks-cli](https://github.com/microcks/microcks-cli) project
- Run the following command in a shell:

```sh
docker run -it microcks/microcks-cli:latest microcks-cli test 'Petstore API <your_login>:1.2.0' {{< param petstore_api_fixed >}} OPEN_API_SCHEMA --microcksURL={{< param microcks_url >}}/api/ --keycloakClientId={{< param microcks_client_id >}} --keycloakClientSecret={{< param microcks_client_secret >}} --waitFor=60sec
```

If everything went fine, you should see something similar to:

```raw
MicrocksClient got status for test "5dc2f6a7d7e470000114d1d4" - success: false, inProgress: true
MicrocksTester waiting for 2 seconds before checking again or exiting.
MicrocksClient got status for test "5dc2f6a7d7e470000114d1d4" - success: true, inProgress: false
```

