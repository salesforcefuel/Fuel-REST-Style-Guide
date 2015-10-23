This method deletes an existing topic filter.

##Resouce

	/v3/topics/{topicId}/keywordGroups/{keywordGroupId}

##HTTP Method

	DELETE

##Request Parameters

	*topicId* - integer value indicating unique ID for topic filter
	*keywordGroupId* - integer value indicating unique UD for keyword group

##Request Parameters Example

	DELETE /v3/topics/{id}

##Sample Request
```
DELETE /v3/topics/123459

##Sample Response

A successful call returns a 204 No Content code.

A call including an invalid ID value returns a 404 code. Ensure your call contains valid values.

An internal server error returns a 500 code. Try your code at a later time.

DELETE /topics/{id}/keywordGroups/{id}