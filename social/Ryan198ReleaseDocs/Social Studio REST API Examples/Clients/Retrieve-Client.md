This method retrieves the organization for your company within the Salesforce Marketing Cloud. At this time, this call returns only the client for the authenticated user.

##Resource

	/v3/clients{id}

##HTTP method

	GET

##Request Parameters

	*id* - string value containing ID of client

##Request Parameter Example

	GET /v3/clients{id}

##Sample Request
```
GET /v3/clients/1
```

##Sample Response
```
{
  "data": [
    {
      "id": "1",
      "title": "Radian6 Technologies",
      "email": null,
      "timeZone": "America/Halifax",
      "languageId": 1,
      "sessionTimeoutMillis": 28800000,
      "aviaryEnabled": false,
      "apiSelfServeEnabled": true
    }
  ],
  "meta": {
    "totalCount": 1
  }
}
```
  *data - object including information on client
    *id* - integer value indentifying organization
    *title* - string value for name of organization
    *email* - string value for email address associated with organization
    *timeZone* - string value for time zone associated with organization
    *languageId* - integer value indicating language associated with organization
    *sessionTimeoutMillis* - integer value indication number of milliseconds associated with timeout value for organization
    *aviaryEnabled* - boolean value indicating whether organization can use aviary
    *apiSelfServeEnabled* - boolean value indicating organization access to API self-service features