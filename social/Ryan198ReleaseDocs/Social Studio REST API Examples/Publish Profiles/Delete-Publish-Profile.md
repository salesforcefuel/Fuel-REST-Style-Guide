This method deletes a publish profile from an account.

##Resource

	/v3/publishprofiles/{id}

##HTTP Method

	DELETE

##Request Parameters

	*id* - string value indicating unique identifier for publish profile

##Request Parameters Example

	DELETE /v3/publishProfiles/{id}

##Sample Call
```
curl -X DELETE {HOST}/v3/publishProfiles/740a25ea-0b57-11e3-8d6f-168170973bd5
```

##Sample Response

A successful call returns the following response:
```
{
    true
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

A call from a user without permission to remove the publish profile returns the following response:
```
{
    "status": "403",
    "code": "error.FORBIDDEN",
    "message": "Unauthorized to view profile"
}
```