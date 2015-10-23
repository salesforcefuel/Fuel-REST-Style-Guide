This method activates an existing topic filter.

##Resouce

	/v3/topics/{id}

##HTTP Method

	POST

##Request Parameters

	*id* - integer value indicating unique ID for topic filter

##Request Parameters Example

	POST /v3/topics/{id}

##Query Parameters

	*action* - string value indicating action to perform on topic filter (required)
		*activate*
	*billingCode* - string value indicating billing code to associated with activation (required)

##Sample Request
```
POST /v3/topics/12345?action=activate&billingCode=6789

##Sample Response

A successful call returns a 204 No Content code.

A call including an invalid ID value returns a 404 code. Ensure your call contains valid values.

An internal server error returns a 500 code. Try your code at a later time.