This method updates an existing approval flow.

##Resource

	/v1/approvalflows

##HTTP method

	PATCH

##Request Parameters

	*id* - ID for the approval flow (required)
	*name* - identifies the name of the workflow. This parameter accepts any unique string value for a specific owner that does not include the < or > characters.
	*priority* - accepts an optional integer value that sets the priority for the workflow

##Request Parameter Examples

	PATCH	/v1/approvalflows/{id}

##Sample Request

This sample request updates an approval flow with a priority of 2:
```
curl -X PATCH -d "priority=2" {HOST}/v1/approvalflows/d460106d-794b-11e3-b8e3-168170973bd5
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

	*status* - string value indicating success of call
	*response* - string value indicating update of approval flow

##Error Responses

An unsuccessful call will return one of the following responses:

*[Bad Argument](Approval-Error-Messages.md)
*[Duplicate Entry](Approval-Error-Messages.md)
*[Unauthorized to Modify Approval Flow](Approval-Error-Messages.md)
*[Workspace Does Not Exist](Approval-Error-Messages.md)