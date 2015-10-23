This method prompts a suspended threshold to resume functionality.

##Resource

	/v2/thresholds/{thresholdId}?method=resume

##HTTP Resource

	POST

##Request Parameters

	*thresholdID* - integer value indicating unique ID for threshold

##Request Parameters Example

	POST /v2/thresholds/{thresholdId}?method=resume

##Sample Request
```
POST /v2/thresholds/{thresholdId}?method=resume
```

##Sample Response

A successful call returns a 201 code.

A call referencing an invalid ID returns a 404 Not Found code. Ensure your call uses the correct ID.

A internal server error occuring during the call returns a 500 code. Try your call again later.