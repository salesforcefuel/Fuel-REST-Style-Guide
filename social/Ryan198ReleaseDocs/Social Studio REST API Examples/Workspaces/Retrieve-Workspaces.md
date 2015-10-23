This method retrieves a paginated list of workspaces within an account.

##Resource

	/v1/workspaces

##HTTP Method

	GET

##Request Parameters

	*page* - integer value indicating which page to display from retreived data (default of 1)
	*perpage* - integer value indicating how many results to include in a page  (value must be greater than 1 and not exceed 25, default of 10)
	*search* - string value indicating which characters to search for at start of workspace name (only at beginning, not within name strings)
	*orderBy* - string value indicating order of returned results:
		*name* - name of workspace (default)
		*updated* - last modified timestamp
	*order* - string value indicating display direction for retrieved content:
		*desc* - descending order
		*asc* - ascending order (default)
	*user* - string value identifying workspace user. This parameter defaults to *default* value. The call ignores other values and returns an error for non-admin users.
	*isMember* - boolean value that pairs with *user* parameter to return on workspaces with an assigned role for the user.
	*visibiility* - string value indicating whether a workspace appears to all users:
		*private* - does not appear (default)
		*public* - does appear
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

	GET /v1/workspaces?

##Sample Request

The call below retrieves the workplaces within an account:
```
GET /v1/workspaces?visibility=public&search=salesforce&include=permissions,membercount
```

##Sample Response

A successful call returns the following response:
```
{
    "status": true,
    "response": [
        {
            "name": "workspace A",
            "id": "46e66860-25fe-11e3-b1a1-168170973bd5",
            "visibility": "public",
            "logo": "a_logo.png",
            "description": "A great workspace",
            "group_id": "123"
        },
        {
            "name": "Workspace B",
            "id": "46f96860-25fe-11e3-b1a1-168170973bd5",
            "visibility": "public",
            "logo": "b_logo.png",
            "description": "B successful workspace",
            "group_id": "234"
        }
    ],
    "meta": {
        "total": 400,
        "page": 2
        "perpage": 2,
        "current": "{HOST}/v1/workspaces?page=2&perpage=2&visibility=public",
        "prev": "{HOST}/v1/workspaces?page=1&perpage=2&visibility=public",
        "next": "{HOST}/v1/workspaces?page=3&perpage=2&visibility=public"
    }
}
```
##Error Responses

A call finding no workspaces returns the following response:
```
{
    "status": true,
    "response": [],
    "meta": {
        "total": 0,
        "page": 1,
        "perpage": 10,
        "current": "{HOST}/v1/workspaces?page=1&perpage=10&visibility=public",
        "prev": "",
        "next": ""
    }
}
```

A call including a bad argument returns the following response:
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

    *status* - string value indicating success of call
    *response* - array of information indicating retrieval of workspaces
        *name* - string value including name of workspace    
        *id* - string value of retrieved workspace
        *visibility* - string value indicating public or private workspace
        *logo* - string value including URL of logo image file
        *description* - string value including description of workspace
        *group_id* - string value including ID of associated group