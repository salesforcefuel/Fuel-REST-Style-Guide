This method retrieves information for a specified user within an account

##Resource

	/v3/users/{id}

HTTP Method

	PUT

##Request Parameters

	*id* - integer value indicating unique ID for user (you may also use the *me* shorthand in place of this value)

##JSON Parameters

	*username* - string value including network username for user (required)
	*displayName* - string value displaying user name (required)
	*email* - string value indicating email address for user (required)
	*timeZone* - string value indicating location for user (required)
	*enabled* - boolean value indicating user status (required)
        *true* - string value indicating enabled (required)
       	*false* - string value indicating disabled user (required)
	*orgRoleId* - integer value indicating role for user within organization (required)
    *internalUserAvatarUrl* - string value indicating location of avatar image file for internal use
    *userAvatarUrl* - string value indicating location of avatar image file
    *languageId* - integer value indicating language used by user

##Request Parameter Example

	PUT /v3/users/{id}

##Sample Request
```
PUT /v3/users/{id}
{
  "username": "Matt.Jones@example.com",
  "displayName": "Matt Jones",
  "email": "Matt.Jones@example.com",
  "timeZone": "Europe/London",
  "enabled": true,
  "avatarURL": "http://a0.twimg.com/profile_images/1284202467/laptop-vector-model-122171296611479Nq0_normal.png",
  "languageId": 1,
  "internalUserAvatarUrl": "http://socialstudio.s3.amazonaws.com/avatars/ad816b59936d93dc3ec36a43e15cbb8c"
}
```

##Sample Response

A successful call returns a 204 No Content code, indicating a successful update.

A call referencing an invalid ID returns a 404 Not Found code. Ensure your call uses the correct ID.

A internal server error occuring during the call returns a 500 code. Try your call again later.