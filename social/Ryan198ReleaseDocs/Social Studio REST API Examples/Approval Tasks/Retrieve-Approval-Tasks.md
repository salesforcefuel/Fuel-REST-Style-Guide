This method retrieves all approval procedures for a specified approval flow.

##Resource

	/v1/approvalprocedures

##HTTP method

	GET

##Request Parameters

	*id* - ID for the approval flow (required)
	*hydrate=argument - indicates that the call should return related entity information instead of string or integer IDs 

##Request Parameter Examples

	GET	/v1/approvalprocedures/{id}

##Sample Request

This sample request retrieves the specified approval flow:
```
curl GET {HOST}/v1/approvalprocedures/aab75fac-0453-11e3-8d6f-168170973bd5
```

##Sample Response

A successful call returns the following response:
```
{
    "status": true,
    "response": {
        "items": [
            {
                "criteria": "user",
                "operator": "equals",
                "argument": 123123,
                "action": "approve"
            },
            {
                "criteria": "user",
                "operator": "equals",
                "argument": 8765,
                "action": "approve"
            },
            {
                "criteria": "user",
                "operator": "equals",
                "argument": 425548144218779,
                "action": "approve"
            }
        ],
        "query": "(1 AND 2) OR ( 1 AND 3 )"
    },
    "meta": []
}
```

A successful call with the hydrate argument returns the following response:
```
{
    "status": true,
    "response": {
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
                    "avatar_url": null,
                    "timezone": "GMT",
                    "enabled": true,
                    "updated": "2014-02-07T18:59:47+0000",
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
                    "avatar_url": null,
                    "timezone": "GMT",
                    "enabled": true,
                    "updated": "2014-02-07T18:59:47+0000",
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
                    "avatar_url": null,
                    "timezone": "GMT",
                    "enabled": true,
                    "updated": "2014-02-07T18:59:47+0000",
                    "organization_id": 10545
                },
                "action": "approve"
            }
        ],
        "query": "1 and ( 2 or 3 )"
    },
    "meta": []
}
```

    *status* - string value indicating success of call
    *response* - array of information related to retrieved rules:
        *items* - array indicating information contained within rule:
             *criteria* - string value indicating object within rule
             *operator* - string value indicating whether criteria EQUALS or NOT EQUALS the supplied argument value
             *argument* - string value to compare with criteria
             *action* - string value indicating action performed via rule
             *query* - string values indicating AND or OR for query with supplied criteria

The information provided with the hydrate argument varies depending on the included entities.

##Error Responses

A call referencing an unknown approval flow returns the following response:
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

Ensure that you reference the correct ID for the approval flow.

A call referencing an approval flow without authorization returns the following response:
```
{
    "status": false,
    "response": {
        "errors": [
            {
                "code": "error.forbidden",
                "message": ""
            }
        ]
    },
    "meta": []
}
```

Ensure you use the correct authentication information.