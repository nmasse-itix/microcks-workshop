# Microcks Workshop

## Requirements

- OpenShift
- Microcks
- Apicurio
- A GitHub platform (either in the cloud or on-premises)

## Setup

- Fork this repo in your GitHub platform
- Deploy the [API Backend](api-backend/nodejs/)
- Update the URLs to match your environments in [config.toml](lab-instructions/config.toml)
- Deploy the workshop instructions in your environment:

```sh
oc new-project microcks-workshop --display-name="Microcks Workshop"
oc new-app centos/nginx-114-centos7:latest~https://github.com/nmasse-itix/microcks-workshop.git --name=microcks-workshop
oc expose svc/microcks-workshop
```

If you want the Red Hat official image, adjust the previous command to replace `centos/nginx-114-centos7:latest` with `registry.access.redhat.com/rhscl/nginx-114-rhel7:latest`. Also, do not forget to change the URL to point to your GIT repository instead!
