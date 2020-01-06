# avro-schemas

Adds completion for Apache Avro schema (.avsc) files using http://json.schemastore.org/avro-avsc

See https://github.com/mtth/avsc/tree/master/etc/schemas for example schemas.

```jsonc  
{
  "type": "record",
  "name": "User",
  "doc": "Inspired by a schema found on https://github.com/ept/avrodoc",
  "fields": [
    {
      "name": "id",
      "type": "int"
    },
    {
      "name": "username",
      "type": "bytes"
    },
    {
      "name": "signupDate",
      "type": "long"
    },
    {
      "name": "emailAddresses",
      "type": {
        "type": "array",
        "items": {
          "type": "record",
          "name": "EmailAddress",
          "fields": [
            {
              "name": "verified",
              "type": "boolean",
              "default": false
            },
            {
              "name": "dateAdded",
              "type": "long"
            },
            {
              "name": "dateBounced",
              "type": [
                "null",
                "long"
              ]
            }
          ]
        }
      }
    },
    {
      "name": "twitterAccounts",
      "type": {
        "type": "array",
        "items": {
          "type": "record",
          "name": "TwitterAccount",
          "fields": [
            {
              "name": "status",
              "type": {
                "type": "enum",
                "name": "OAuthStatus",
                "symbols": [
                  "PENDING",
                  "ACTIVE",
                  "DENIED",
                  "EXPIRED",
                  "REVOKED"
                ]
              }
            },
            {
              "name": "userId",
              "type": "long"
            },
            {
              "name": "dateAuthorized",
              "type": "long"
            }
          ]
        }
      }
    }
  ]
}
```
