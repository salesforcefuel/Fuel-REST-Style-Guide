This method creates a new keyword query topic filter.

##Resouce

	/v3/topics

##HTTP Method

	POST

##Request Parameters

	None

##Request Parameters Example

	POST /v3/topics

##JSON Parameters

	*title* - string value indicating name for new topic filter (required)
	*languages* - array of integer valuess indicating languages associated with new topic filter (required, set with value of ALL to associate with all available values)
	*mediaTypes* - array of integer valuess indicating media types associated with new topic filter (required, set with value of ALL to associate with all available values)
	*regions* - array of integer valuess indicating regions assocaited with new topic filter (required, set with value of ALL to associate with all available values)
	*status* - integer value indicating status of topic profile (create with value of 4 for DRAFT, otherwise leave blank)

##Sample Request
```
POST /v3/topics
{
  "title": "test topic profile",
  "languages": [
    "1"
  ],
  "mediaTypes": [
    {
      "id": "5"
    },
    {
      "id": "1"
    },
    {
      "id": "10"
    }
  ]
  "regions":  [
  	   "all"
  ]
}

##Sample Response

A successful call returns a 201 Success code with a Location response header including the URL for the new topic filter resource.

A call including a malformed JSON payload or invalid IDs (such as unauthorized mediatypes) returns a 400 code. Ensure your JSON payload contains valid values.

A call by a user with insufficient permissions returns a 403 code. Ensure your user can make this call within your organization.

An internal server error returns a 500 code. Try your code at a later time.