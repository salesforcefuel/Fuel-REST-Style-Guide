This method retrieves information on a publish profile from an account.

##Resource

	/v3/publishprofiles/{id}

##HTTP Method

	GET

##Request Parameters

	*id* - string value indicating unique identifier for publish profile

##Request Parameters Example

	GET /v3/publishProfiles/{id}

##Sample Call
```
GET /v3/publishprofiles/740a25ea-0b57-11e3-8d6f-168170973bd5
```

##Sample Response

A successful call returns the following response:
```
{
    “id”: “740a25ea-0b57-11e3-8d6f-168170973bd5”,
    "type": "publish",
    "name": "My Publish Profile",
    "description": "testing",
    "owner": 6834,
    "created": 'created_date',
    "socialPropertyIds": '/v3/publishProfiles/:id/socialPropertyIds',
    "targetingIds": '/v3/publishProfiles/:id/targetingIds'
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