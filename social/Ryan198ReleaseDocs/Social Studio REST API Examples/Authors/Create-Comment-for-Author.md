This method creates a comment for the specified author.

##Resource

	/v3/authors/{id}/comments

##HTTP Method

	POST

##Request Parameters

	*id* - string value indicating the author of a post (required)

##Request Parameters Example

	POST /v3/authors/{id}/comments

##Sample Request
```
POST /v3/authors/{id}/comments
Content-Type:application/json
{
        "value": "i heart talk radio"
}
```

##Sample Response

A successful call returns a 201 code with the applicable Location header.

A call including an invalid JSON object returns a 400 code.

A call including an invalid author returns a 404 code.

A call encountering an internal server error while adding the comment returns a 500 code.