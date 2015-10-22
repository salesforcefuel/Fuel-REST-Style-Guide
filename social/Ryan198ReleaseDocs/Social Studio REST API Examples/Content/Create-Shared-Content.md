This method creates shared content for use within a workspace.

##Resource

	/v1/clips/

##HTTP Method

	POST

##Request Parameters

	None

##Request Parameter Example

	POST /v1/clips

##JSON Parameters

Each JSON payload includes information on the shared content:

	*message* - string value indicating the message to share (required). The JSON payload must include a *message* value or an *assets* value. You can include both.
	*assets* - string value indicating URL and type of content (required). The JSON payload must include a *message* value or an *assets* value. You can include both.
	*workspaces* - string value identifying the workspace in which you can access the content (required).
	*workspace_id* - string value identifying owner of shared content (required). You can leave this value blank.
	*description* - string value containing text describing the shared content.
	*post_id* - string value containing a GUID for the shared content.
	*clip_id* - string value containing a GUID for a clip created from existing shared content.

##Sample Request

The call below creates a new piece of shared content with the specified message:
```
{
    "message": "This is a test message",
    "workspaces": ["c2e918d2-4309-11e3-bb55-1cb63b08732d"],
    "workspace_id": "584d3ad3-2f7b-11e3-b8e3-168170973bd5"
}
```

The call below creates a new piece of shared content with the specified asset:
```
{
    "assets": [{"url":"http://www.foo.com", "type":2}}],
    "workspaces": ["c2e918d2-4309-11e3-bb55-1cb63b08732d"],
    "workspace_id": "584d3ad3-2f7b-11e3-b8e3-168170973bd5"
}
```

The call below creates a new piece of shared content and shares it to the specified workspaces:
```
{
    "message": "This is a test message",
    "workspace_id": "584d3ad3-2f7b-11e3-b8e3-168170973bd5",
    "description": "This is a test comment",
    "assets": [{"url":"http://www.foo.com", "type":3, "metadata":"{\"url\":\"http://www.foo.com\"}"}],
    "workspaces": ["c2e918d2-4309-11e3-bb55-1cb63b08732d"]
}
```

The call below creates a new piece of shared content containing an image from an existing post:
```
{
    "post_id": "82e6c061-2c5a-11e3-b1a1-168170973bd5"
    "message": "This is a test message",
    "workspace_id": "584d3ad3-2f7b-11e3-b8e3-168170973bd5",
    "description": "This is a test comment",
    "assets": [{"url":"http://www.foo.com/images/foo.png", "type":2}],
    "workspaces": ["c2e918d2-4309-11e3-bb55-1cb63b08732d"]
}
```

The call below duplicate a piece of shared content containing an link from an existing clip:
```
{
    "clip_id": "82e6c061-2c5a-11e3-b1a1-168170973bd5"
    "message": "This is a test message",
    "workspace_id": "584d3ad3-2f7b-11e3-b8e3-168170973bd5",
    "description": "This is a test comment",
    "assets": [{"url":"http://www.foo.com", "type":3}],
    "workspaces": ["c2e918d2-4309-11e3-bb55-1cb63b08732d"]
}
```

##Sample Response

A successful call returns the following response:
```
# HTTP 201 Created
{
    status: true,
    response: {
        id: "35543aba-18b2-4995-bb76-ea1132fe544a",
    },
    meta: {},
}
```

    *status* - string value indicating success of call
    *id* - string value indicating ID for newly created content