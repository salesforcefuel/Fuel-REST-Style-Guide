This method returns all source filter queries associated with a social filter.

##Resource

	/v3/sourceFilters/{sourceFilterId}/sourceFilterQueries

##HTTP Method

	GET

##Request Parameters

	*sourceFilterId* - integer value indicating the source filter from which to retrieve a social filter query (required)

##Query Parameters

	*limit* - integer value indicating number of results to return (defaults to 5000)
	*offset* - integer value indicating result to start with (defaults to 0)
	*q* - string value including characters to search for in title (minimum of 3 characters)
	*orderBy* - string values indicating how call sorts returned list of source filters:
		*id* - sort by ID value
		*title* - sort by title
		*uri* - sort by URI

##Request Parameter Example

	GET /v3/sourceFilters{id}/sourceFilterQueries

##Sample Request
```
GET /v3/sourceFilters/1/sourceFilterQueries
```

##Sample Response
```
{
  "data": [
    {
      "id": "1",
      "title": "Source Filter Query Title",
      "uri": "my.source.filter.query.org"
    }
  ],
  "meta": {
    "totalCount": 1
  }
}
```

	*data - array of objects including information on returned source filters
		*id* - integer value indicating unique identifier for source filter
		*title* - string value indicating name for source filter
		*uri* - string value including source filter query location in system