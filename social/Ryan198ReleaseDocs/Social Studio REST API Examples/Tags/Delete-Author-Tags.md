This method deletes all tag values associated with an author object within your account.

##Resource

	/v3/authors/{authorId}/tags

##HTTP Method

	DELETE

##Request Parameters

	*authorId* - Integer value indicating the ID of the specific author (required)

##Request Parameters Example

	DELETE /v3/authors/{authorId}/tags

##Sample Request
```
DELETE /v3/authors/12345/tags
```

#Sample Response

A successful call returns a 204 code.

A call that could not remove all tags from an author returns a 400 code.

A call referencing an invalid author ID will return a 404 code. Ensure you referenced the correct author value.

A internal error during creation returns a 500 Internal Server Error. Try your create call again at a later time.