This method updates to any rules included in an approval flow.

##Resource

	/v1/approvalprerequisites

##HTTP method

	PUT

##Request Parameters

	*approvalflow* - ID for the approval flow (required)

##Request Parameter Example

	PUT {HOST}/v1/approvalprerequisites/46e66860-25fe-11e3-b1a1-168170973bd5

##JSON Parameters

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

	*query* - string value indicating how approval workflow handles criteria

	The *query* argument includes integers, logical operators, and appropriate groupings.
		*integer* - position of criteria in *items* array, beginning with 1
		*logical operators* - AND or OR value indicating grouping of criteria
		*grouping* - Use parantheses to group together integers and logical operators. You cannot use AND and OR in the same grouping.

##Sample Request

```
PUT {HOST}/v1/approvalprerequisites/46e66860-25fe-11e3-b1a1-168170973bd5
{
    "items": [
        {
            "criteria": "submitter",
            "operator": "equals",
            "argument": 123123
        },
        {
            "criteria": "social account",
            "operator": "equals",
            "argument": 68304
        },
        {
            "criteria": "social account",
            "operator": "equals",
            "argument": 68647
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

A call referencing a nonexistant approval flow returns the following response:
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

A call not authorized to modify the approval flow returns the following response:
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

A call including incorrect arguments returns the following response:
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