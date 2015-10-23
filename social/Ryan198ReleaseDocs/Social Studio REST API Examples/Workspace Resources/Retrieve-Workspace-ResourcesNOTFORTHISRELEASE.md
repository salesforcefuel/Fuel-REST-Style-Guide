This method retrieves a workspace resource within a workspace.

##Resource

	v1/workspaceresources

##HTTP Method

	GET

##Request Parameters

	*resource_type* - string value indicating a valid workspace resource (required).
	*workspace_id* - string value indicating the workspace ID (required).
	*exclude_added* - string value indicating call will return resources not added to a workspace group.

##Request Parameter Example

	GET /v1/workspaceresources?

##Sample Request

The call below retrieves a the specified workplace resource:
```
GET /v1/workspaceresources?workspace_id=44dfccf0-ed00-4988-a256-0913281dcb89&resource_type=topic_profile
```

##Sample Response

A successful call returns the following response:
```
{
    "status": true,
    "response": {
        "topics": {
            "data": [
                {
                    "id": "19212",
                    "link": "https://stg2-api.dev.ca1.sfmc.co/socialcloud/v2/topics/19212",
                    "updated": "2014-05-15T03:00:01Z",
                    "title": "This is a test",
                    "creator": {
                        "id": "7626",
                        "link": "https://stg2-api.dev.ca1.sfmc.co/socialcloud/v2/users/7626",
                        "updated": "2014-05-18T13:01:51Z",
                        "title": "super_rich_stage2"
                    },
                    "visibility": "public",
                    "access": "write",
                    "status": 3,
                    "emv": 44900,
                    "languages": [],
                    "mediaTypes": [],
                    "regions": [],
                    "groups": [
                        {
                            "id": "8152",
                            "link": "https://stg2-api.dev.ca1.sfmc.co/socialcloud/v2/workspaceGroups/8152",
                            "updated": "2014-05-18T13:01:51Z",
                            "title": "Richard's New Workspace"
                        }
                    ]
                },
                {
                    "id": "19213",
                    "link": "https://stg2-api.dev.ca1.sfmc.co/socialcloud/v2/topics/19213",
                    "updated": "2014-05-15T03:00:01Z",
                    "title": "This is a new one",
                    "creator": {
                        "id": "7626",
                        "link": "https://stg2-api.dev.ca1.sfmc.co/socialcloud/v2/users/7626",
                        "updated": "2014-05-18T13:01:51Z",
                        "title": "super_rich_stage2"
                    },
                    "visibility": "public",
                    "access": "write",
                    "status": 3,
                    "emv": 2900,
                    "languages": [],
                    "mediaTypes": [],
                    "regions": [],
                    "groups": []
                }
            ],
            "structure": null
        }
    },
    "meta": []
}
```