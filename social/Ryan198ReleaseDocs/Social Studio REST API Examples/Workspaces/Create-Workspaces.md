This method creates a workspace within a Social Studio account.

##Resource

	/v1/workspaces

##HTTP Method

	POST

##Request Parameters

	*name* - string value containing name of new workspace (required). This value includes a maximum of 255 characters. The call removes leading and trailing whitespaces. The call replaces multiple consecutive whitespaces with a single whitespace.
	*visibiility* - string value indicating whether a workspace appears to all users:
		*private* - does not appear (default)
		*public* - does appear
	*description* - string value containing text describing the new workspace (defaults to empty string)
	*logo* - string value indicating the location of a workspace image file (defaults to empty string)

##Request Parameter Example

	POST /v1/workspaces

##Sample Request

The call below creates a new piece of shared content with the specified message:
```
POST -d "name=A new workspace for the system" -d "visibility=private" -d "logo=workspace_logo.png" -d "description=A brand new workspace." {HOST}/v1/workspaces
```

##Sample Response

A successful call returns the following response:
```
{
    "status": true,
    "response": {
        "id": "95b75fac-0453-11e3-8d6f-168170973bd5"
    },
    "meta": []
}
```

##Error Responses

An unsuccessful call due to a duplicate name returns the following response:
```
{
    "status": false,
    "response": {
        "errors": [
            {
                "code": "error.conflict",
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

    *status* - string value indicating success of call
    *response* - string value indicating creation of workspace
        *id* - string value indicating ID of newly created workspace