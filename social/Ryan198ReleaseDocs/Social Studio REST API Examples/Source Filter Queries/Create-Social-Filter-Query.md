This method creates a source filter query within an account. You can add this source filter query to the source filter to create conditions for use within the filter.

##Resource

	/v3/sourceFilters/{sourceFilterId}/sourceFilterQueries

##HTTP Method

	POST

##Request Parameters

	*sourceFilterId* - integer value indicating the source filter from which to retrieve a social filter query (required)

##Request Parameter Example

	POST /v3/sourceFilters/{sourceFilterId}/sourceFilterQueries

##JSON Parameters

	*title* - string value indicating name for source filter
	*uri* - string value indicating location for source filter query(required)

##Sample Request
```	
POST	/v3/sourceFilters/1/sourceFilterQuery
{
    "title": "Source Filter Title",
    "uri": "A description of what this source filter contains."
}
```

##Sample Response

A successful call returns a 201 Success response. A Location response header contains the URL to the new source filter query resource.

A malformed JSON payload returns a 400 Bad Request response. Ensure your payload matches the sample shown in this example.

A internal error during creation returns a 500 Internal Server Error. Try your create call again at a later time.