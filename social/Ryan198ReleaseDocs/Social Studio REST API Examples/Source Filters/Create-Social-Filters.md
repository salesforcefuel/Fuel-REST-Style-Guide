This method creates a source filter within an account. You can then add source filter queries to the source filter and create conditions for use within the filter.

##Resource

	/v3/sourceFilters

##HTTP Method

	POST

##Request Parameters

	None

##Request Parameter Example

	POST /v3/sourceFilters

##JSON Parameters

	*title* - string value indicating name for source filter (create)
	*description* - string value including text describing source filter (create)
	*public* - boolean value indicating whether the source filter includes a public status

##Sample Request
```	
POST	/v3/sourceFilters/
{
    "title": "Source Filter Title",
    "description": "A description of what this source filter contains.",
    "public": false
}
```

##Sample Response

A successful call returns a 201 Success response. A Location response header contains the URL to the new source filter resource.

A malformed JSON payload returns a 400 Bad Request response. Ensure your payload matches the sample shown in this example.

A internal error during creation returns a 500 Internal Server Error. Try your create call again at a later time.