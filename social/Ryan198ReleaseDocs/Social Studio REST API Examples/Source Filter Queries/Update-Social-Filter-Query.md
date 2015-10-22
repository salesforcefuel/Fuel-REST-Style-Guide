This method updates a source filter query within an account.

##Resource

	/v3/sourceFilters/{sourceFilterId}/sourceFilterQueries/{sourceFilterQueryId}

##HTTP Method

	PUT

##Request Parameters

	*sourceFilterId* - integer value indicating the source filter from which to retrieve a social filter query (required)
	*sourceFilterQueryId* - integer value indicating the source filter query to retrieve (required)

##Request Parameter Example

	PUT /v3/sourceFilters/{sourceFilterId}/sourceFilterQueries/{sourceFilterQueryId}

##JSON Parameters

	*title* - string value indicating name for source filter
	*uri* - string value indicating location for source filter query(required)

##Sample Request
```	
PUT	/v3/sourceFilters/1
{
    "title": "Source Filter Title",
    "uri": "A description of what this source filter contains."
}
```

##Sample Response

A successful call returns a 204 No Content response, indicating the call successfully updated the source filter.

A malformed JSON payload returns a 400 Bad Request response. Ensure your payload matches the sample shown in this example.

A internal error during creation returns a 500 Internal Server Error. Try your create call again at a later time.