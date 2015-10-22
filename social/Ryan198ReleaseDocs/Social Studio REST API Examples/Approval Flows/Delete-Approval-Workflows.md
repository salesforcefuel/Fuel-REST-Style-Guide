This method deletes an existing approval flow.

##Resource

	/v1/approvalflows

##HTTP method

	DELETE

##Request Parameters

	*id* - ID for the approval flow (required)

##Request Parameter Examples

	DELETE	/v1/approvalflows/{id}

##Sample Request

This sample request updates an approval flow with a priority of 2:
```
DELETE {HOST}/v1/approvalflows/d460106d-794b-11e3-b8e3-168170973bd5
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
	*response* - string value indicating deletion of approval flow

##Error Responses

An unsuccessful call will return one of the following responses:

*[Approval Flow Does Not Exist](Approval-Error-Messages.md)
*[Missing Argument](Approval-Error-Messages.md)
*[Unauthorized to Remove Approval Flow](Approval-Error-Messages.md)