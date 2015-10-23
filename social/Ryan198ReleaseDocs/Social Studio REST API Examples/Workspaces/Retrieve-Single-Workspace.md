This method retrieves a single workspace within an account.

##Resource

	/v1/workspaces

##HTTP Method

	GET

##Request Parameters

	*id* - string value identifying the workspace to retrieve
	*include* - comma-separated string values of additional information to include:
		*permissions* - string value containing user permissions for the workspace
		*defaultPublishProfile* - string value of default publish profile for workspace
			*view* - can view social assets and posts
			*edit_content* - same as *view* and can create content (such as posts)
			*admin* - same as *edit_content* and can perform admin actions on workspace
			*delete* - can delete workspace
		*membercount* - string value containing total number of users for workspace
		*socialassetcount* - string value containing total number of social assets for workspace
		*engage* - string value containing user engage permissions

##Request Parameter Example

	GET /v1/workspaces/{id}

##Sample Request

The call below retrieves the specified workplace:
```
GET /v1/workspaces/46e66860-25fe-11e3-b1a1-168170973bd5?include=permissions,membercount
```

##Sample Response

A successful call returns the following response:
```
{
    "status": true,
    "response": {
        "name": "A new workspace for the system",
        "id": "46e66860-25fe-11e3-b1a1-168170973bd5",
        "visibility": "private",
        "logo": "workspace_logo.png",
        "description": "A brand new workspace!",
        "group_id": "123"        
    },
    "meta": []
}
```

A call returning information on a private workspace the user cannot access returns the following response:
```
{
    "status": true,
    "response": {
        "name": "PRIVATE WORKSPACE",
        "id": "46e66860-25fe-11e3-b1a1-168170973bd5",
        "visibility": "private"
    },
    "meta": []
}
```

A call including additional information returns the following response:
```
{
    "status": true,
    "response": {
        "id": "46e66860-25fe-11e3-b1a1-168170973bd5",
        "visibility": "public",
        "name": "A new workspace for the system",
        "logo": "",
        "description": "",
        "group_id": "123",
        "permissions": [
            "view",
            "edit_content",
            "admin",
            "delete"
        ],
        "membercount": 100,
        "socialassetcount": 50,
        "engage": [
            "view",
            "edit"
        ]
    },
    "meta": []
}
```

##Error Responses

A call referencing an invalid workspace returns the following response:
```
{
    "status": false,
    "response": {
        "errors": [
            {
                "code": "error.not_found",
                "message": ""
            }
        ]
    },
    "meta": []
}
```

A call including an invalid ID returns the following response:
```
{
    "status": false,
    "response": {
        "errors": [
            {
                "code": "error.bad_request",
                "message": ""
            }
        ]
    },
    "meta": []
}
```

    "status": true,
    "response": {
        "id": "46e66860-25fe-11e3-b1a1-168170973bd5",
        "visibility": "public",
        "name": "A new workspace for the system",
        "logo": "",
        "description": "",
        "group_id": "123",
        "permissions": [
            "view",
            "edit_content",
            "admin",
            "delete"
        ],
        "membercount": 100,
        "socialassetcount": 50,
        "engage": [
            "view",
            "edit"
        ]
    },
    "meta": []
}

    *status* - string value indicating success of call
    *response* - array of information regarding retrieval of workspace
        *id* - string value of retrieved workspace
        *visibility* - string value indicating public or private workspace
        *name* - string value including name of workspace
        *logo* - string value including URL of logo image file
        *description* - string value including description of workspace
        *group_id* - string value including ID of associated group
        *permissions* - array of string values indicating permissions associated with workspace
            *view*
            *edit_content*
            *admin*
            *delete*
        *membercount* - integer value including number of worksapce members
        *socialassetcount* - integer value including number of worksapce members
        *engage* - array of actions associated with engage functions in workspace
            *view*
            *"edit*