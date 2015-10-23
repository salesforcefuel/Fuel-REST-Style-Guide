This method deletes a workspace resource within a workspace.

##Resource

	v1/workspaceresources

##HTTP Method

	DELETE

##Request Parameters

	None

##Request Parameter Example

	DELETE /v1/workspaceresources

##JSON Parameters

Each JSON payload includes information on the shared content:

	*workspace_id* - string value identifying owner of workspace resources (required).
	*resource_type* - string value indicating type of workspace resource created by the call.
	*resource_id* - string value containing identifier for the workspace resource.

##Sample Request

The call below creates a new piece of shared content with the specified message:
```
DELETE	/v1/workspaceresources
{
    "workspace_id": "44dfccf0-ed00-4988-a256-0913281dcb89",
    "resource_type": "topic_profile",
    "resource_id": "19212"
}
```

##Sample Response

A successful call returns the following response:
```
{
    "status": true,
    "response": {
        "resource_type": "topic_profile",
        "resource_id": "19212",
        "workspace_group_id": "8152"
    },
    "meta": []
}
```

    *status* - string value indicating success of call
    *response* - string value indicating deletion of workspace resource
        *resource_type* - string value indicating type of workspace resource created by the call
        *resource_id* - string value containing identifier for the workspace resource
        *workspace_group_id* - string value identifying owner of workspace group