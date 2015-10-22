This method resets the password for an internal user account. A successful call also sends an email message (from support@radian6.com) containing a link the user can click to set a new password value. This call requires administrative privileges.

##Resources

	/v3/users/{userId}/password?action=rest

##HTTP Method

	POST

##Request Parameters

	*userId* - integer value indicating unique ID for user (also accepts me shorthard)

##Request Parameters Example

	POST /v3/users/{id}/password?method=reset

##Sample Request
```
POST /v3/users/12345/password?action=reset
```

##Sample Response

A successful call returns a 204 No Content code, indicating a successful update.

A call referencing an invalid ID returns a 404 Not Found code. Ensure your call uses the correct ID.

A internal server error occuring during the call returns a 500 code. Try your call again later.