This method posts a commment to a specified clip within a workspace.

##Resource

	/v1/clips/

##HTTP Method

	POST

##Request Parameters

	*id* - ID for the clip (required)

##Request Parameter Example

	POST  /v1/clips/{ID}/comments

##JSON Parameters

Each JSON payload includes information on the shared content:

	*workspace_id* - string value identifying owner of shared content (required).
	*comment* - string value including the text for the comment (required).

##Sample Request

The call below shares the specified content:
```
POST v1/clips/35543aba-18b2-4995-bb76-ea1132fe544a/comment
{
    "workspace_id": "c2e918d2-4309-11e3-bb55-1cb63b08732d",
    "comment": "This is a test comment"
}
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