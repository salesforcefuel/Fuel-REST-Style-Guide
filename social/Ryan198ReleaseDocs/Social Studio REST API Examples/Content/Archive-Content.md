This method archives and unarchives content within a workspace.

##Resource

	/v1/clips/

##HTTP Method

	POST

##Request Parameters

	*id* - ID for the clip (required)
	*action* - string value indicating the action to perform on the content:
		*archive* - archive the content, making it available for review but not for use
		*unarchive* - unarchive the content and make it avaiable for use

##Request Parameter Example

	POST  /v1/clips/{ID}?action=archive

##Sample Request

The call below archives the specified content:
```
POST v1/clips/35543aba-18b2-4995-bb76-ea1132fe544a?action=archive
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