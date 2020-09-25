# Update API schema in Postman via CLI/script

## Install postmanctl

https://github.com/kevinswiber/postmanctl

## Setup

Retrieve necessary IDs:

*API ID*
```
postmanctl get apis
```

*API Version*
```
postmanctl get api-version --for-api {{apiId}}
```

*Schema ID*
```
postmanctl get schema --for-api {{apiId}} --for-api-version {{apiVersionId}}
```

## Run

```
postmanctl replace schema {{schemaId}} --for-api {{apiId}} --for-api-version {{apiVersionId}} --filename ~/dev/schemaDetails.json
```

Where `schemaDetails.json` looks like:

```
{
  "language": "yaml",
  "schema": "updated schema here",
  "type": "openapi3"
}
```
