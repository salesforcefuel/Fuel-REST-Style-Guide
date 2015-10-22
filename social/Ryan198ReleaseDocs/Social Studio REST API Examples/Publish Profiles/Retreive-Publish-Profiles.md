This method retrieves information on publish profiles from an account.

##Resource

	/v3/publishprofiles

##HTTP Method

	GET

##Request Parameters

	none

##Query Parameters

	*workspace* - string value indicating the unique ID for the workspace from which to retrieve publish profiles (required)
	*page* - integer value indicating which page to display from retreived data (defaults to 1)
	*limit* - integer value indicating the number of results to display per page (defaults to 20)
	*orderBy* - string value indicating parameter used to sort results (defaults to date)
	*order* - string value indicating display order for retrieved content:
		*desc* - descending order 
		*asc* - ascending order (default)
	*search* - string value indicating charaters to search for in name, returns paginated results from name matches

##Request Parameters Example

	GET /v3/publishProfiles

##Sample Call
```
curl '{HOST}/v3/publishProfiles?workspace=028e2d63-0914-11e3-8d6f-168170973bd5&page=2&limit=2'
```

##Sample Response

A successful call returns the following response:
```
{
    "publishProfiles": [
        {
            “id”: “000ca3cf-3ed1-4b7d-8253-0d50fe1e93fd”,
            "type": "publish",
            "name": "My Publish Profile",
            "description": "testing",
            "owner": 6834,
            "created": 'created_date',
            "socialPropertyIds": '/v3/publishProfiles/:id/socialPropertyIds',
            "youtubePlaylists": '/v3/publishProfiles/:id/youtubePlaylists',
            "targetingIds": '/v3/publishProfiles/:id/targetingIds'
        },
        {
            “id”: “000ca3cf-3ed1-4b7d-8253-0d50fe1e93fd”,
            "type": "publish",
            "name": "My Publish Profile",
            "description": "testing",
            "owner": 6834,
            "created": 'created_date',
            "socialPropertyIds": '/v3/publishProfiles/:id/socialPropertyIds',
            "targetingIds": '/v3/publishProfiles/:id/targetingIds'
        }
    ],
    "count": 4,
    "next": "{HOST}/v3/publishProfiles?limit=2&workspace=:workspaceId&page=2"
}
```

	*id* - string value indicating unique identifier for publish profile
	*type* - string value indicating type of profile
		*publish*
	*name* - string value indicating name of publish profile
	*description* - string value indicating description of publish profile
	*owner* - integer value indicating unique ID for publish profile owner
	*created* - timestamp value indicating date of creation for publish profile
	*socialPropertyIds* - array of integer values indicating social properties associated with publish profile
	*targetingIds* - array of string values indicating the social network and the category to target

A bad request returns a 400 error and the following response:
```
{
    "status": 400,
    "code": "error.bad_request",
    "message": "Invalid data supplied."
}
```

A call that finds no publish profiles returns the following response:
```
{
    "publishProfiles": []
}