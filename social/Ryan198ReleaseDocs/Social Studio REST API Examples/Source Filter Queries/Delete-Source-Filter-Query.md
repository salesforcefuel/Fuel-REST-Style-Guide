This method deletes the source filter query specified by the ID. This action removes the souce query filter from any associated source filter.

##Resource

	/v3/sourceFilters/{sourceFilterId}/sourceFilterQueries/{sourceFilterQueryId}

##HTTP Method

	DELETE

##Request Parameters

	*sourceFilterId* - integer value indicating the source filter from which to retrieve a social filter query (required)
	*sourceFilterQueryId* - integer value indicating the source filter query to retrieve (required)

##Request Parameter Example

	DELETE	/v3/sourceFilters/{sourceFilterId}/sourceFilterQueries/{sourceFilterQueryId}

##Sample Request

	DELETE /v3/sourceFilters/1/socialFilterQueries/123

##Sample Response

A successful call returns a No Content 204 code, indicating the call succeded and no content exists. 

An internal error occuring during the call returns a 500 error.