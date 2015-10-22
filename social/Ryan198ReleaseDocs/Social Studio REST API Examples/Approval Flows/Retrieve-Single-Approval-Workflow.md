This method retrieves one or more approval flows for a workspace.

##Resource

    /v1/approvalflows

##HTTP method

	GET

##Request Parameters

	*id* - identifies the approval flow to retrieve (required)
	*include* - idenfies optional additional information on the workflow. Possible values include the following:
		*prerequisite* - displays array value of rules within approval flow
		*procedure* - returns array value of procedures
		*approverCount* - returns integer value of approvers for approval flow
		*criteriaCount* - returns integer value of criteria for approval flow
	*hydrate=argument - indicates that the call should return related entity information instead of string or integer IDs 

##Request Parameter Example

	GET {HOST}/v1/approvalflows/{id}

##Sample Request
```
GET /v1/approvalflows/ownerId=a272b824-bbf7-4a8c-bb1e-3d9695f3032a&include=prerequisite,procedure,approvercount,criteriacount&hydrate=argument
```

##Sample Response

A successful call returns the following response:
```
{
    "status": true,
    "response": {
        "id": "d460106d-794b-11e3-b8e3-168170973bd5",
        "ownerId": "92ed3d44-5376-11e3-b8e3-168170973bd5",
        "ownerType": "workspace",
        "priority": 171,
        "triggerAction": "publish",
        "name": "My Approval Flow"
    }
}
```

A successful call with include parameters returns the following response:
```
{
    "status": true,
    "response": {
        "id": "e1c69b8c-6844-43fb-9eb3-0fe30dd92cc3",
        "ownerId": "7046e184-0bd1-4c88-9255-642d8a212f31",
        "ownerType": "workspace",
        "priority": 7,
        "triggerAction": "publish",
        "name": "testworkflowapi",
        "prerequisite": {
            "items": [
                {
                    "criteria": "submitter",
                    "operator": "equals",
                    "argument": 6721
                },
                {
                    "criteria": "social account",
                    "operator": "equals",
                    "argument": "1a4ebec4-7b11-4d0a-aad3-4fc859ba8e28"
                },
                {
                    "criteria": "social account",
                    "operator": "equals",
                    "argument": "d5594362-829d-49c6-b317-6675b9a280f8"
                }
            ],
            "query": "( 1 and 2 ) or 3"
        },
        "procedure": {
            "items": [
                {
                    "criteria": "user",
                    "operator": "equals",
                    "argument": 6721,
                    "action": "approve"
                },
                {
                    "criteria": "user",
                    "operator": "equals",
                    "argument": 6721,
                    "action": "approve"
                }
            ],
            "query": "1 or 2"
        },
        "meta": {
            "criteriacount": "4"
            "approvercount": "1"
        }
    },
    "meta": []
}
```

A successful call with include parameters and the hydrate argument returns the following response:
```
{
    "status": true,
    "response": {
        "id": "e1c69b8c-6844-43fb-9eb3-0fe30dd92cc3",
        "ownerId": "7046e184-0bd1-4c88-9255-642d8a212f31",
        "ownerType": "workspace",
        "priority": 7,
        "triggerAction": "publish",
        "name": "testworkflowapi",
        "prerequisite": {
            "items": [
                {
                    "criteria": "submitter",
                    "operator": "equals",
                    "argument": {
                        "id": 6721,
                        "email": "pboddu@example.com",
                        "username": "pboddu@example.com",
                        "title": "PraveenBoddu",
                        "display_name": "PraveenBoddu",
                        "timezone": "GMT",
                        "enabled": true,
                        "updated": "2014-02-26T20:14:47+0000",
                        "organization_id": 10545
                    }
                },
                {
                    "criteria": "social account",
                    "operator": "equals",
                    "argument": null
                },
                {
                    "criteria": "social account",
                    "operator": "equals",
                    "argument": null
                }
            ],
            "query": "( 1 and 2 ) or 3"
        },
        "procedure": {
            "items": [
                {
                    "criteria": "user",
                    "operator": "equals",
                    "argument": {
                        "id": 6721,
                        "email": "pboddu@example.com",
                        "username": "pboddu@example.com",
                        "title": "PraveenBoddu",
                        "display_name": "PraveenBoddu",
                        "timezone": "GMT",
                        "enabled": true,
                        "updated": "2014-02-26T20:14:47+0000",
                        "organization_id": 10545
                    },
                    "action": "approve"
                },
                {
                    "criteria": "user",
                    "operator": "equals",
                    "argument": {
                        "id": 6721,
                        "email": "pboddu@example.com",
                        "username": "pboddu@example.com",
                        "title": "PraveenBoddu",
                        "display_name": "PraveenBoddu",
                        "timezone": "GMT",
                        "enabled": true,
                        "updated": "2014-02-26T20:14:47+0000",
                        "organization_id": 10545
                    },
                    "action": "approve"
                }
            ],
            "query": "1 or 2"
        }
    },
    "meta": []
}
```

    *status* - string value indicating success of call
    *response* - array of information related to retrieved approval flows:
        *id* - string value indicating ID of approval flow
        *ownerId* - string value indicating ID of approval flow owner
        *ownerType* - string value indicating entity type of approval flow owner
        *priority* - integer value indicating priority for apprival flow
        *triggerAction* - string value indicating action that begins approval flow
        *name* - string value indicating name of approval flow
        *prerequisites* - array indicating rules contained within approval flow:
            *criteria* - string value indicating object within rule
            *operator* - string value indicating whether criteria EQUALS or NOT EQUALS the supplied argument value
            *argument* - string value to compare with criteria
            *query* - string values indicating AND or OR for query with supplied criteria

The information provided with the hydrate argument varies depending on the included entities.

##Error Responses

An unsuccessful call will return one of the following error responses:

*[Bad Argument](Approval-Error-Messages.md)
*[Missing Argument](Approval-Error-Messages.md)
*[Unauthorized to View Workspace](Approval-Error-Messages.md)

