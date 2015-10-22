This method retrieves information for all users within an account

##Resource

	/v3/users

HTTP Method

	GET

##Request Parameters

	None

##Query Parameters

	*q* - string value including characters to search for in title (minimum of 3 characters)
	*enabled* - boolean value indicating whether to retrieve only active users
		*true* - string value indicating return only active users
		*false* - string value indicating return all users
	*limit* - integer value indicating number of results to return (defaults to 100,000)
	*offset* - integer value indicating result to start with (defaults to 0)

##Sample Request
```
GET	/v3/users
```

##Sample Response

A successful call returns the following response:
```
{
  "data": [
    {
      "id": "3339",
      "title": "Admin",
      "username": "admin",
      "displayName": "Admin",
      "email": "testuser@example.com",
      "timeZone": "America/Goose_Bay",
      "enabled": true,
      "orgRoleId": 1,
      "languageId": 1,
      "createdDate": "2014-05-09T03:00:00Z",
      "internalUserAvatarUrl": null,
      "userAvatarUrl": null,
      "clientId": 1
    },
    …
  ],
  "meta": {
    "totalCount" : 52
  }
}
```

	*data* - array of user objects returned by call
		*id* - integer value indicating unique ID for user
		*title* - string value including name fo users
        *username* - string value including network username for user
        *email* - string value including email address for user
        *timeZone* - string value indicating location for user
        *enabled* - boolean value indicating user status
        	*true* - string value indicating enabled
        	*false* - string value indicating disabled user
    	*orgRoleId* - integer value indicating role for user within organization
    	*languageId* - integer value indicating language used by user
    	*createdDate* - timestamp value indicating when system created user
    	*internalUserAvatarUrl* - string value indicating location of avatar image file for internal use
    	*userAvatarUrl* - string value indicating location of avatar image file
    	*clientId* - integer value indicating client ID for specific user