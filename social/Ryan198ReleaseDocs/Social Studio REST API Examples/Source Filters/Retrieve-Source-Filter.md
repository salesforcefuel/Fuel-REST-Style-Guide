This method returns a source filter specified by the ID value.

##Resource

	/v3/sourceFilters/{sourceFilterId}

##HTTP Method

	GET

##Request Parameters

	*sourceFilterId* - integer value indicating ID for source filter

##Request Parameter Example

	GET /v3/sourceFilters/{sourceFilterId}

##Sample Request
```
GET /v3/sourceFilters/1
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
  ],
  "meta": {
    "totalCount": 1
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
