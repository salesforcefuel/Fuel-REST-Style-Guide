This method retrieves one or more approval flows for a workspace.

##Resource

    /v1/approvalflows

##HTTP method

	GET

##Request Parameters

	*ownerId* - identifies the workspace from which to retrieve the approval flows (required)
	*ownerType* - identifies the object from which to retrieve the approval flows (required). Possible values include the following:
		*workspace*
	*include* - idenfies optional additional information on the workflow. Possible values include the following:
		*prerequisite* - displays array value of rules within approval flow
		*procedure* - returns array value of procedures
		*approverCount* - returns integer value of approvers for approval flow
		*criteriaCount* - returns integer value of criteria for approval flow
	*page* - indicates optional number of pages to provide for results
	*perpage* - indicats optional number of results to provide per page

##Request Parameter Example

	GET {HOST}/v1/approvalflows

##Sample Request
```
GET /v1/approvalflows?ownerId=a272b824-bbf7-4a8c-bb1e-3d9695f3032a&ownerType=workspace
```

##Sample Response

A successful call returns the following response:
```
{
    "status": true,
    "response": [
        {
            "id": "d460106d-794b-11e3-b8e3-168170973bd5",
            "ownerId": "92ed3d44-5376-11e3-b8e3-168170973bd5",
            "ownerType": "workspace",
            "priority": 1,
            "triggerAction": "publish",
            "name": "My Approval Flow"
        },
        {
            "id": "b64ee373-81f0-11e3-b8e3-168170973bd5",
            "ownerId": "92ed3d44-5376-11e3-b8e3-168170973bd5",
            "ownerType": "workspace",
            "priority": 2,
            "triggerAction": "publish",
            "name": "My Other Approval Flow"
        }
    ],
    "meta": {
        "total": 2,
        "page": 1,
        "perpage": 2,
        "current": "HOST/v1/approvalflows?workspace=92ed3d44-5376-11e3-b8e3-168170973bd5&page=1",
        "prev": "",
        "next": ""
    }
}
```

A successful call with include parameters returns the following response:
```
{
    "status": true,
    "response": [
        {
            "id": "d460106d-794b-11e3-b8e3-168170973bd5",
            "ownerId": "92ed3d44-5376-11e3-b8e3-168170973bd5",
            "ownerType": "workspace",
            "priority": 99,
            "triggerAction": "publish",
            "name": "Workflow get with include",
            "prerequisite": {
                "items": [
                    {
                        "criteria": "submitter",
                        "operator": "equals",
                        "argument": 7664
                    },
                    {
                        "criteria": "submitter",
                        "operator": "equals",
                        "argument": 7641
                    },
                    {
                        "criteria": "language",
                        "operator": "equals",
                        "argument": 60
                    },
                    {
                        "criteria": "language",
                        "operator": "equals",
                        "argument": 61
                    }
                ],
                "query": "1 and 2 and ( 3 or 4 )"
            },
            "procedure": [],
            "meta": {
                "criteriacount": "4"
                "approvercount": "1"
            }
        }
    ],
    "meta": {
        "total": 1,
        "page": 1,
        "perpage": 1,
        "current": "HOST/v1/approvalflows?include=prerequisite,procedure&workspace=92ed3d44-5376-11e3-b8e3-168170973bd5&page=1",
        "prev": "",
        "next": ""
    }
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

##Error Responses

An unsuccessful call will return one of the following error responses:

*[Bad Argument](Approval-Error-Messages.md)
*[Missing Argument](Approval-Error-Messages.md)
*[Unauthorized to View Workspace](Approval-Error-Messages.md)
