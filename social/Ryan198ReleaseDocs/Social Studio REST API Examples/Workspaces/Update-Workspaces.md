This method updates a workspace within a Social Studio account.

##Resource

	/v1/workspaces

##HTTP Method

	PATCH

##Request Parameters

	*id* - string value containing the ID value for the workspace (required)
	*name* - string value containing name of new workspace. This value includes a maximum of 255 characters. The call removes leading and trailing whitespaces. The call replaces multiple consecutive whitespaces with a single whitespace.
	*visibiility* - string value indicating whether a workspace appears to all users:
		*private* - does not appear (default)
		*public* - does appear
	*description* - string value containing text describing the new workspace (defaults to empty string)
	*logo* - string value indicating the location of a workspace image file (defaults to empty string)

##Request Parameter Example

	PATCH /v1/workspaces/{id}

##Sample Request

The call below creates a new piece of shared content with the specified message:
```
PATCH -d "visibility=private" {HOST}/v1/workspaces/46e66860-25fe-11e3-b1a1-168170973bd5
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
    *response* - string value indicating updating of workspace