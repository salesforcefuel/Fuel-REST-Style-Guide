This method deletes the source filter specified by the ID

##Resource

	/v3/sourceFilters

##HTTP Method

	DELETE

##Request Parameters

	*sourceFilterId* - integer value indicating ID for source filter

##Request Parameter Example

	DELETE	/v3/sourceFilters/{id}

##Sample Request

	DELETE /v3/sourceFilters/1

##Sample Response

A successful call returns a No Content 204 code, indicating the call succeded and no content exists. 

An internal error occuring during the call returns a 500 error.