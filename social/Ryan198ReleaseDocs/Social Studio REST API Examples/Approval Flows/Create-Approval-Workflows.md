This method creates an approval flow for a workspace.

##Resource

	/v1/approvalflows

##HTTP method

	POST

##Request Parameters

	*workspace* - ID for the workspace (required)
	*trigger* - identifies the event that begins the workflow process. This parameter accepts the following string values:
		*publish*
	*name* - identifies the name of the workflow. This parameter accepts any unique string value for a specific owner that does not include the < or > characters.
	*priority* - accepts an optional integer value that sets the priority for the workflow

##Request Parameter Example

	POST {HOST}/v1/approvalflows

##Sample Request
```
POST /v1/approvalflows HTTP/1.1
Host: HOST
Content-Type: application/x-www-form-urlencoded

trigger=publish&workspace=92ed3d44-5376-11e3-b8e3-168170973bd5&priority=9&name=My+Approval+Flow
```

##Sample Response

A successful call returns the following response:
```
{
    "status": true,
    "response": {
        "id": "d460106d-794b-11e3-b8e3-168170973bd5"
    },
    "meta": []
}
```

	*status* - string value indicating success of call
	*id* - string value indicating ID for newly created approval flow

##Error Responses

An unsuccessful call will return one of the following error responses:

*[Bad Argument](Approval-Error-Messages.md)
*[Duplicate Entry](Approval-Error-Messages.md)
*[Missing Argument](Approval-Error-Messages.md)
*[Unauthorized to Add Approval Flow](Approval-Error-Messages.md)
*[Workspace Does Not Exist](Approval-Error-Messages.md)