# Graphql Schema to JSON converter


### How to use
```
const convert = require('gql-json-converter');
const jsonSchema = convert(schema);
console.log(jsonSchema);
```

### Output
```
{
  "type": {
    "User": {
      "id": {
        "type": "Int",
        "array": false,
        "required": true
      },
      "name": {
        "type": "String",
        "array": false,
        "required": true
      },
      "avatar": {
        "type": "Photo",
        "array": false,
        "required": false
      }
    },
    "Message": {
      "id": {
        "type": "Int",
        "array": false,
        "required": true
      },
      "text": {
        "type": "String",
        "array": false,
        "required": false
      },
      "user": {
        "type": "User",
        "array": false,
        "required": false
      }
    },
    "Query": {
      "user": {
        "type": "User",
        "array": false,
        "required": false
      },
      "users": {
        "type": "Users",
        "array": true,
        "required": false
      },
      "message": {
        "type": "Message",
        "array": false,
        "required": false
      },
      "messages": {
        "type": "Message",
        "array": true,
        "required": false
      }
    },
    "Mutation": {
      "createUser": {
        "args": {
          "data": {
            "type": "UserInput",
            "array": false,
            "required": true
          }
        },
        "type": "User",
        "array": false,
        "required": false
      },
      "createMessage": {
        "args": {
          "text": {
            "type": "String",
            "array": false,
            "required": false
          }
        },
        "type": "Message",
        "array": false,
        "required": false
      },
      "uploadPhotos": {
        "args": {
          "data": {
            "type": "PhotoInput,",
            "array": true,
            "required": false
          },
          "repository": {
            "type": "ID,",
            "array": false,
            "required": false
          }
        },
        "type": "Photo",
        "array": true,
        "required": false
      }
    },
    "Subscription": {
      "messageCreated": {
        "args": {
          "repository": {
            "type": "Int",
            "array": false,
            "required": false
          }
        },
        "type": "Message",
        "array": false,
        "required": false
      }
    }
  },
  "input": {
    "PhotoInput": {
      "file": {
        "type": "String",
        "array": false,
        "required": true
      },
      "name": {
        "type": "String",
        "array": false,
        "required": true
      }
    },
    "UserInput": {
      "name": {
        "type": "String",
        "array": false,
        "required": true
      },
      "photo": {
        "type": "InputPhoto",
        "array": false,
        "required": false
      }
    }
  },
  "schema": {
    "query": {
      "type": "Query",
      "array": false,
      "required": false
    },
    "mutation": {
      "type": "Mutation",
      "array": false,
      "required": false
    },
    "subscription": {
      "type": "Subscription",
      "array": false,
      "required": false
    }
  }
}
```
