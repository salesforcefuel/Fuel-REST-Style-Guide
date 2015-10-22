This method returns all source filters associated with an account.

##Resource

	/v3/sourceFilters

##HTTP Method

	GET

##Request Parameters

	*limit* - integer value indicating number of results to return (defaults to 5000)
	*offset* - integer value indicating result to start with (defaults to 0)
	*q* - string value including characters to search for in title (minimum of 3 characters)
	*title* - string value including characters to search for an exact title match
	*status* - string value including comma-separated list of status values to search:
		*0* - deactivated source filters
		*2* - active source filters
		*3* - draft source filters
	*orderBy* - string values indicating how call sorts returned list of source filters:
		*id* - sort by ID value
		*title* - sort by title
		*visibility* - sort by visibility
		*status* - sort by status
		*creation* - sort by creation date
		*description* - sort by description
		*creator* - sort by creator display name
		*ASC* - sort in ascending order
		*DESC* - sort in descending order

##Request Parameter Example

	GET /v3/sourceFilters

##Sample Request
```
GET /v3/sourceFilters?status=2
```

##Sample Response

{
  "data": [
    {
      "id": "1",
      "title": "Trent - Yahoo Answers SF",
      "description": null,
      "status": 2,
      "createdDate": "2009-12-22T17:22:08Z",
      "topicCount": 0,
      "public": false,
      "creator": {
        "id": "58",
        "link": "https://api.radian6.com/socialcloud/v2/users/58",
        "updated": null,
        "title": "Trent - Staging - GMail - CLID  = 1"
      }
    },
    ...
  ],
  "meta": {
    "totalCount": 706
  }
}

	*data - array of objects including information on returned source filters
		*id* - integer value indicating unique identifier for source filter
		*title* - string value indicating name for source filter
		*description* - string value including text describing source filter
		*status* - integer value indicating status of source filter
		*createdDate* - timestamp value indicating date of creation for source filter
		*topicCount* - integer value indicating topics associated with source filter
		*public* - boolean value indicating whether the source filter can be viewed publicly
		*creator* - object including information on user who created the source filter
			*id* - integer value indicating unique identifier for user
			*link* - string value including URL for user
			*updated* - timestamp value indicating last time user updated their information (can be null)
			*title* - string value indicating name of user
