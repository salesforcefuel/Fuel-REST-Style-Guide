This method retrieves activity associated with a specific clip within a workspace.

##Resource

	/v1/clips/

##HTTP Method

	GET

##Request Parameters

	*id* - ID for the specified clip

##Request Parameter Example

	GET /clips/{id}/activities

##Sample Request

	GET /clips/35543aba-18b2-4995-bb76-ea1132fe544a/activities

##Sample Response

A successful call returns the following response:
```
# HTTP 200 Success
{
    "status": true,
    "response":[
    {
     "user_id": "6883",
     "organization_id": "10567",
     "activity_name": "audit.post.clip.used",
     "date": "2014-05-29 17:45:36",
     "metadata": {
        "workspace": "My workspace",
        "comment": null,
        "changes":[]
     }
    },
    {
     "user_id": "6883",
     "organization_id": "10567",
     "activity_name": "audit.clip.comment",
     "date": "2014-05-29 17:45:36",
     "metadata": {
        "workspace": null,
        "comment": "This is so good",
        "changes":[]
     }
    },
    {
     "user_id": "6883",
     "organization_id": "10567",
     "activity_name": "audit.clip.created",
     "date": "2014-05-29 17:45:36",
     "metadata": {
        "workspace": "My workspace",
        "comment": null,
        "changes":[]
      }
    }
    ]
    "meta":[]
}
```

  *status* - string value indicating success of call
  *response* - array of information on content activities
    *userId* - string value indicating user interacting with clip
    *organizationId* - string value indicating organization associated with activity
    *activity_name* - string value action performed on clip, such as commenting or creation
    *date* - timestamp value indicating when activity took place
    *metadata* - array of information associated with activity
        *workspace* - string value indicating name of workspace
        *comment* - string value indicating text of any associated comment
        *changes* - array listing any changes associated with activity