This method deletes a macro within an account.

##Resource

	/v2/macros/{id}

##HTTP Method

	DELETE

##Request Parameters

	*id* - integer value indicating unique ID for macro

##Request Parameters Example

	DELETE /v2/macros/{id}

##Sample Request
```
DELETE /v2/macros/{id}
```

##Sample Reponse

A successful call returns a No Content 204 code, indicating the call succeded and no content exists. 

A call that matches no macro ID value returns a 404 Not Found code.

An internal error occuring during the call returns a 500 code.