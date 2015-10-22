This method deletes content within a workspace.

##Resource

	/v1/clips/

##HTTP Method

	DELETE

##Request Parameters

	*ID* - ID for the clip (required)

##Request Parameter Example

	DELETE	/v1/clips/{ID}

##Sample Request

The call below deletes the specified content:
```
DELETE v1/clips/35543aba-18b2-4995-bb76-ea1132fe544a
```

##Sample Response

A successful call returns the following response:
```
# HTTP 200 Success
{
    "status": true,
    "response": {},
    "meta": {},
}
```

	*status* - string value indicating success of call