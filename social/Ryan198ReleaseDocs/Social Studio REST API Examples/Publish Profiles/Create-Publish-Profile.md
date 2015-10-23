This method creates a publish profile within an account.

##Resource

	/v3/publishProfiles

##HTTP Method

	POST

##Request Parameters

	None

##JSON Parameters

	*name* - string value indicating name of publish profile (required)
	*description* - string value including description of publish profile (required)
	*socialPropertyIds* - array of integer values indicating social properties associated with publish profile
	*youtubePlaylists* - array of key and value pairs indicating the account and playlists associated with the publish profile
	*targetingIds* - array of string values indicating the social network and the category to target
	*webAnalytics* - array of key and value pairs indicating web analytical information to include with publish profile

##Request Parameter Example

POST /v3/publishProfiles

##Sample Request
```
curl -X POST  {HOST}/v3/publishProfiles
{
        "name": "My Publish Profile",
        "description": "My Publish Profile Description",
        "socialPropertyIds": ['3211', '4567'],
        "youtubePlaylists": [
            {
                "key" : "3211",
                "value" : "11"
            },
            {
                "key" : "3211",
                "value" : "22"
            }
        ],
        "targetingIds": ['li_ag', 'fb_nj'],
        "webAnalytics": [
            {
                "key" : "sample_key",
                "value" : "sample_value"
            },
            {
                "key" : "sample_key2",
                "value" : "sample_value2"
            }
        ]
    }
```

##Sample Response

A successful call returns an ID value for the newly created publish profile:
```
{
    "id":"5239534f-0b58-11e3-8d6f-168170973bd5"
}
```

A bad request returns a 400 error and the following response:
```
{
    "status": 400,
    "code": "error.bad_request",
    "message": "Invalid data supplied."
}
```