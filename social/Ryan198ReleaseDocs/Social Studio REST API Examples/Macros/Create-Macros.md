This method creates a macro within an account. This macro can contain several different actions within the JSON payload, indicating actions to perform when the macro receives an execute call.

##Resource

	/v2/macros

##HTTP Method

	POST

##Request Parameters

	None

##Request Parameters Example

	POST /v2/macros

##JSON Parameters

	*name* - string value indicating name for macro (required)
	*description* - string value including text describing the macro
	*action* - array of actions included within macro:
		*SetClassification* - integer value indicating media type classification to add 
		*AddAuthorTag* - string value to add as tag to author object
		*AddPostTag* - string value to add as tag to post object
		*AssignUser* - integer value identifying post to assign to user
		*SetEngagement* - integer value identifying engagement level to set
		*SetPriority* - integer value identifying priority level to set
		*AddPostNote* - string value to add to post as note 
		*SetSpamStatus* - integer value used to set spam status
			*0* - not spam
			*2* - spam
		*AddSourceTag* - string value to add as source tag 
		*SetSentiment* - integer value to set as sentiment level
		*SendToSalesforceScs* - integer value used to set organization to which the macro will send post                                                                              *case* - string value indicating whether to create case
			*off* - do not create case (default)
			*on* -  create case
		*lead* - string value indicating whether to create lead
			*off* - do not create lead (default)
			*on* -  create lead

##Sample Request
```
POST /v2/macros
{
	"actions": [
		{
		    "type": "AddPostTag",
		    "value": "Post Tag",
		    "parameters": [
	    		{
	      			"name": "nameValue",
	      			"value": "parameterValue"
	    		}
			]
		}
	]
}
```

##Sample Response

A successful call returns the following response:
```
{
  "id": 1234,
  "name": "My Macro",
  "description": "Macro Description",
  "owner": 3349,
  "client": 112,
  "createdDate": "2015-10-22T15:29:26+00:00",
  "modifiedDate": "2015-10-22T15:29:26+00:00",
  "actions": [
     <AddAuthorTag American>
  ]
}

	*id* - integer value indicating unique ID for macro
	*owner* - integer value indicating unique ID for owner of macro
	*client* - integer value indicating unique ID for client containing macro (read-only)
	*createdDate* - timestamp value indicating when system created macro (read-only)
	*modifiedDate* - timestamp value indicating when system last updated macro (read-only)