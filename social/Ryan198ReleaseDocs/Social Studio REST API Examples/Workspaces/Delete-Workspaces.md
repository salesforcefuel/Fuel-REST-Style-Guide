This method deletes a workspace within a Social Studio account.

##Resource

	/v1/workspaces

##HTTP Method

	DELETE

##Request Parameters

	*id* - string value containing the ID value for the workspace

##Request Parameter Example

	DELETE /v1/workspaces/{id}

##Sample Request

The call below creates a new piece of shared content with the specified message:
```
DELETE {HOST}/v1/workspaces/46e66860-25fe-11e3-b1a1-168170973bd5
```

##Sample Response

A successful call returns the following response:
```
{
    "status": true,
    "response": true,
    "meta": []
}
```

##Error Responses

An call referencing a nonexistant workspace returns the following response:
```
{
    "status": false,
    "response": {
        "errors": [
            {
                "code": "error.not.found",
                "message": ""
            }
        ]
    },
    "meta": []
}
```

An unsuccessful call due to a bad parameter returns the following response:
```
{
    "status": false,
    "response": {
        "errors": [
            {
                "code": "error.bad_request",
                "message": ""
            }
        ]
    },
    "meta": []
}
```

An unsuccessful call due to insufficient permissions returns the following response:
```
{
    "status": false,
    "response": {
        "errors": [
            {
                "code": "error.forbidden",
                "message": ""
            }
        ]
    },
    "meta": []
}
```

    *status* - string value indicating success of call
    *response* - string value indicating deletion of workspace