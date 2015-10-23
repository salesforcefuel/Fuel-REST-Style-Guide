This method retrieves information on a specified property from a publish profile in an account.

##Resource

	/v3/publishprofiles/{id}/{type}

##HTTP Method

	GET

##Request Parameters

	*id* - string value indicating unique identifier for publish profile (required)
	*type* - string value indicating property to retrieve:
		*targetingIds* - array of string values indicating the social network and the category to target
		*socialPropertyIds* - array of integer values indicating social properties associated with publish profile
		*webAnalytics* - array of key and value pairs indicating web analytical information to include with publish profile

##Request Parameters Example

	GET /v3/publishProfiles/{id}/{type}

##Sample Call
```
GET /v3/publishprofiles/740a25ea-0b57-11e3-8d6f-168170973bd5/targetingIds
```

##Sample Response

A successful call for targeting IDs returns the following response:
```
{
    "targetingIds": [
        "li_geo_af.dz",
        "li_geo_af.eg"
    ],
    "count": 9,
    "next": "{HOST}/v3/publishProfiles/0151bc2e-ee3d-4108-b7cf-b3bb0d207b91/targetingIds&page=2"
}
```

A successful call for targeting IDs returns the following response:
```
{
    "webAnalytics": [
        {
            "key": "another one",
            "value": "another value"
        },
        {
            "key": "third one",
            "value": "third value"
        },
        {
            "key": "ytm_dd",
            "value": "ytm_value"
        }
    ],
    "count": 3,
    "next": null
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

A call that finds no publish profile returns the following response:
```
{
    "status": "404",
    "code": "error.not_found",
    "message": "publish profile not found"
}
```