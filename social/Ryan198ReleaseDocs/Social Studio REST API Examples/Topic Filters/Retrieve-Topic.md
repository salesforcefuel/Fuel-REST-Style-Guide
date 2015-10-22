This method retrieves a specific keyword query topic filter based on the user organization role and any access the user has to shared topic profiles via project membership. You cannot use this route to retrieve information on keyword groups and queries.

##Resource

	/v3/topics/{id}

##HTTP Method

	GET

##Request Parameters

	*id* - integer value indicating unique ID for topic filter

##Request Parameters Example

	GET /v3/topics{id}

##Sample Call
```
GET /v3/topics/4
```

##Sample Response

A successful call returns the following response:
```
{
  "data": [
    {
      "id": "4",
      "title": "Scott Test 3",
      "creator": {
        "id": "3",
        "link": "https://stg2-dmz3.dev.ca1.example.co/socialcloud/v2/users/3",
        "updated": null,
        "title": "scott@example.com (clientId = 1)"
      },
      "visibility": "private",
      "status": 1,
      "emv": 0,
      "languages": [],
      "mediaTypes": [],
      "regions": [],
      "keywordGroups": [],
      "billingCode": "",
      "includeSourceFilters": [],
      "excludeSourceFilters": [],
      "includeAllSourceFilters": [],
      "createdDate": "2009-10-09T19:27:58Z"
    },
    …
  ],
  "meta" : {
       "totalCount" : 52
  }
}
```

	*id* - integer value indicating unique ID for topic filter
	*title* - string value indicating name of topic filter
	*creator* - object containing information on creator of topic filter:
		*id* - integer value indicating unique ID for creator
		*link* - string value indicating URL for location of creator
		*updated* - timestamp value indicating last update for creator (can be null)
		*title* - string value indicating name of creator
	*visibility* - string value indicating visibility of topic filter
		*public*
		*private*
	*status* - integer values indicating status of topic filter to return
		*0* - disabled
		*1* - purchased or active
		*2* - trial
		*3* - expired
		*4* - draft
	*emv* - integer value indicating estimated monthly value for topic filter
	*languages* - array of language values associated with topic filter
	*mediaTypes* - array of media type values associated with topic filter
	*regions* - array of region values associated with topic filter
	*keywordGroups* - array of keyword group values associated with topic filter
	*billingCode* - string value of billing code associated with topic filter
	*includeSourceFilters* - array of source filters associated with topic filter
	*excludeSourceFilters* - array of source filters specifically excluded from topic filter
	*includeAllSourceFilters* - array of all source filters available for topic filter
