This method prompts an active threshold to suspend functionality.

##Resource

	/v2/thresholds/{thresholdId}?method=suspend

##HTTP Resource

	POST

##Request Parameters

	*thresholdID* - integer value indicating unique ID for threshold

##Request Parameters Example

	POST /v2/thresholds/{thresholdId}?method=suspend

##Sample Request
```
POST /v2/thresholds/{thresholdId}?method=suspend
```

##Sample Response

A successful call returns a 201 code.

A call referencing an invalid ID returns a 404 Not Found code. Ensure your call uses the correct ID.

A internal server error occuring during the call returns a 500 code. Try your call again later.