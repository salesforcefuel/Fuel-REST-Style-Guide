This method DELETES the specified threshold with the information provided in the call.

##Resource
	
	/v2/thresholds/{thresholdID}

##HTTP Method

DELETE

##Request Parameters

	*thresholdID* - integer value indicating unique ID for threshold

##Request Parameters Example

	DELETE /v2/thresholds{thresholdID}

##Sample Request
```
DELETE /v2/thresholds1234
```

##Sample Response

A successful call returns a 204 Content Not Found code, indicating the deletion process succeeded.

A call referencing an invalid ID returns a 404 Not Found code. Ensure your call uses the correct ID.

A internal server error occuring during the call returns a 500 code. Try your call again later.