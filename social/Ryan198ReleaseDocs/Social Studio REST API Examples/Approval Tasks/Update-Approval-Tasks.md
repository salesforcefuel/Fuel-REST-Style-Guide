This method updates approval procedures for a specified approval flow.

##Resource

	/v1/approvalprocedures

##HTTP method

	PUT

##Request Parameters

	*id* - ID for the approval flow (required)

##Request Parameter Example

	PUT	/v1/approvalprocedures/{id}

#JSON Parameters

Each JSON payload includes two arguments:

	*items* - array of criteria to add or update to the approval flow

	The *items* array includes individual items with the following values:

		*criteria* - string value indicating the subject of the rule. Acceptable values include the following:
			*label* - label associated with object
			*submitter* - user ID for person performing submit action 
			*social account* - social property ID associated with the object
			*language* - language associated with the object
			*country* - country associated with the object
		*operator* - string value indicating whether the rule subject equals or does not equal the provided value
			*equals*
			*not equals*
		*argument* - string value to match against the *criteria* value. *argument* can accept empty values for label, country, and language. *argument* cannot accept empty values for *submitter* or *social account*.
		*action* - indicates the action for the rule. Acceptable values include the following:
			*approve*

	*query* - string value indicating how approval workflow handles criteria

	The *query* argument includes integers, logical operators, and appropriate groupings.
		*integer* - position of criteria in *items* array, beginning with 1
		*logical operators* - AND or OR value indicating grouping of criteria
		*grouping* - Use parantheses to group together integers and logical operators. You cannot use AND and OR in the same grouping.

##Sample Request

This sample request updates an approval flow with a priority of 2:
```
curl -X PUT {HOST}/v1/approvalprocedures/46e66860-25fe-11e3-b1a1-168170973bd5
{
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
}
```

##Sample Response

A successful call returns the following response:
```
{
    "status": true,
    "response": true,
    "meta": []
}
```

    *status* - string value indicating success of call
    *response* - string value indicating update of approval flow

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

Ensure you used the correct ID for the approval flow.

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

A call referencing a bad request returns the following response:
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

Ensure you properly formatted the information included in the call.