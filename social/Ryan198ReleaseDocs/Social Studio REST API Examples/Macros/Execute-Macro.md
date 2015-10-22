This method executes a macro within an account.

##Resource

	/v2/macros/{id}

##HTTP Method

	POST

##Request Parameters

	*id* - integer value indicating unique ID for macro

##Query Parameters

	*method* - string value indicating action to perform
		*execute*

##JSON Parameters

	*posts* - array of integer values identifying posts included in the running macro
	*topics* - array of integer values identifying topics included in the running macro

##Request Parameters Example

	POST /v2/macros/{id}

##Sample Request
```
POST /v2/macros/{id}?method=execute
{
	"posts": [
		2345
	]
}
```

##Sample Reponse

A successful call returns the following response:
```
{
  "results": [
    {
      "postId": <2345>,
      "action": "AddPostTag",
      "result": "SUCCESS",
      "error": ""
    }
  ]
}
```

	*results* - object including data on macro execution
		*postId* - integer value indicating post on which macro performed
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
			*SendToSalesforceScs* - integer value used to set organization to which the macro will send post                                                               
			*case* - string value indicating whether to create case
				*off* - do not create case (default)
				*on* -  create case
			*lead* - string value indicating whether to create lead
				*off* - do not create lead (default)
				*on* -  create lead