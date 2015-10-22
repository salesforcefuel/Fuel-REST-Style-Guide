This method deletes a comment from the specified author.

##Resource

	/v3/authors/{id}/comments/{commentId}

##HTTP Method

	DELETE

##Request Parameters

	*id* - string value indicating the author of a post (required)
	*commentId* - string value indicating the comment to delete (required)

##Request Parameters Example

	DELETE /v3/authors/{id}/comments/{commentId}

##Sample Request
```
DELETE /v3/authors/{id}/comments/{commentId}
```

##Sample Response

A successful call returns a 204 No Content code.

A call including an invalid author, a previously deleted note, or a nonexistant note returns a 404 code.

A call encountering an internal server error while deleting the comment returns a 500 code.