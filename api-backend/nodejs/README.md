# Petstore API

## Deploy

```sh
oc new-project petstore-api --display-name="Petstore API"
oc new-app --name=petstore-api openshift/nodejs~https://github.com/nmasse-itix/microcks-workshop.git --context-dir=api-backend/nodejs/
oc expose svc/petstore-api --hostname=petstore-api.app.itix.fr
oc new-app --name=petstore-api-fixed openshift/nodejs~https://github.com/nmasse-itix/microcks-workshop.git --context-dir=api-backend/nodejs/ -e RETURN_200_ON_CREATE=true
oc expose svc/petstore-api-fixed --hostname=petstore-api-fixed.app.itix.fr
```

## Usage

### List all pets

```sh
curl http://localhost:8080/pets/
```

### Get a pet

```sh
curl http://localhost:8080/pets/1
curl http://localhost:8080/pets/2
```

### Create a pet

```sh
curl -XPOST http://localhost:8080/pets/ -H 'Content-Type: application/json' -d '{"name":"Raspoutine","tag":"dog"}'
```

### Update a pet

```sh
curl -XPUT http://localhost:8080/pets/3 -H 'Content-Type: application/json' -d '{"id":3,"name":"Daisy","tag":"turtle"}'
```

### Delete a pet

```sh
curl -XDELETE http://localhost:8080/pets/3
```

## Reset

Remove the Jenkins pipeline:

```sh
oc delete -n petstore-api bc/petstore-pipeline
```

Remove the 3scale services:

```sh
ansible-playbook cleanup/cleanup.yml -e admin_portal_hostname=[TENANT]-admin.3scale.net -e threescale_token=[REDACTED]
```

Go to the [Apicurio Studio](https://apicurio-studio.app.itix.fr/apis) and remove the **Petstore** service.

Go to the Microcks console and remove the **Petstore** service.

Remove the OpenAPI Specification file from this repository:

```sh
git rm openapi-spec.yaml
git commit -m 'reset the demo'
git push
```
