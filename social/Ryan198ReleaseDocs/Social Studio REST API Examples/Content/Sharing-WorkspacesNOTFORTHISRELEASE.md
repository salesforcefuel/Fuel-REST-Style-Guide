This method shares or unshares workspaces based on the IDs included in the call. Existing workspaces not included in the set become unshared, while new workspaces not already shared become shared.

##Resource

	/v1/clips/

##HTTP Method

	PATCH

##Request Parameters

	*id* - ID for the specified clip

##Request Parameter Sample

	PATCH /clips/{id}

##JSON Parameters

Each JSON payload includes information on the shared content:

	*set_id* - workspaces to share

##Sample Request
```
	PATCH /clips/c2e918d2-4309-11e3-bb55-1cb63b08732d
```

##Sample Response

A successful call returns the following response:
```
# HTTP 200 Success
{
    "status": true,
    "response": {
        "id": "9f8ecfbc-650b-4fe6-b830-c90276ff7b2b",
        "source_type": "1",
        "source_type_id": "6845",
        "organization_id": "10560",
        "archived": "0",
        "deleted": "0",
        "message": "This is a message",
        "description": null,
        "start_date": null,
        "end_date": null,
        "created": "2014-07-29 19:01:23",
        "updated": "2014-07-29 19:01:23",
        "author": {
            "id": "6845",
            "display_name": "Collin Lee",
            "avatar_url": null
        },
        "assets": [],
        "owner_workspace": {
            "id": "4073bc0d-f9b3-4de8-8978-03665226aa05",
            "owner": "1",
            "name": "One",
            "logo": null
        },
        "shared_workspace_count": 4,
        "shared_workspaces": [
            {
                "id": "808e0d8a-1258-4c44-9be3-54d5a162626a",
                "name": "!ANA-Clips",
                "logo": "https://d2ee3wvl22m8i7.cloudfront.net/33486e2b56386fc7dd8c1821c1311c9c7de21619/w/imgs/1403795296331_339539_10150424222266583_1907745049_o.jpg"
            },
            {
                "id": "ab8b7a66-6949-4d2e-aaf7-fe923421cd23",
                "name": "13thMay2014",
                "logo": "https://d2ee3wvl22m8i7.cloudfront.net/33486e2b56386fc7dd8c1821c1311c9c7de21619/w/imgs/1403291121206_2ndgoal.gif"
            },
            {
                "id": "c38cab01-0aa8-4222-a04b-1f0d76fd62a7",
                "name": "collin test 123",
                "logo": null
            },
            {
                "id": "e7c8d276-2e0b-45db-84f3-88ae19b797aa",
                "name": "Collin Test",
                "logo": null
            }
        ],
        "post_count": 0,
        "metrics": []
    },
    "meta": []
}
```
