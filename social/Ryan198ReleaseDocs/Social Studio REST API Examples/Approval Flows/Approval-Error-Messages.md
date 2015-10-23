Approval flow calls returning an error can return one of the following responses:

##Bad Argument

A call included an invalid or unsupported argument key and value pair returns the following response:
```
{
    "status": false,
    "response": {
        "errors": [
            {
                "code": "error.bad_request",
                "message": "An invalid parameter/value was supplied"
            }
        ]
    },
    "meta": []
}
```

Ensure that your call includes only valid values.

##Duplicate Entry

A call attempting to create or update an entity that already uses the same unique identifiers returns the following response:
```
{
    "status": false,
    "response": {
        "errors": [
            {
                "code": "error.conflict",
                "message": "A duplicate entry was detected when saving"
            }
        ]
    },
    "meta": []
}
```

Ensure that your new call includes a unique value.

##Missing Argument

A call not including an expected argument returns the following repsonse:
```
{
    "status": false,
    "response": {
        "errors": [
            {
                "code": "error.bad_request",
                "message": "An expected argument was not supplied"
            }
        ]
    },
    "meta": []
}
```

Ensure that your call includes all required values.

##Unauthorized to Add Approval Flow

A call attempting to add an approval flow without the proper permissions returns the following response:

```
{
    "status": false,
    "response": {
        "errors": [
            {
                "code": "error.forbidden",
                "message": "Unathorized to remove"
            }
        ]
    },
    "meta": []
}
```

Ensure that you include the proper authentication with your call.

##Unauthorized to Modify Approval Flow

A call attempting to modify an approval flow without the proper permissions returns the following response:

```
{
    "status": false,
    "response": {
        "errors": [
            {
                "code": "error.forbidden",
                "message": "Unathorized to modify"
            }
        ]
    },
    "meta": []
}
```

Ensure that you include the proper authentication with your call.

##Unauthorized to Remove Approval Flow

A call attempting to remove an approval flow without the proper permissions returns the following response:

```
{
    "status": false,
    "response": {
        "errors": [
            {
                "code": "error.forbidden",
                "message": "Unathorized to remove"
            }
        ]
    },
    "meta": []
}
```

Ensure that you include the proper authentication with your call.

##Unauthorized to View Approval Flow

A call attempting to View an approval flow without the proper permissions returns the following response:

```
{
    "status": false,
    "response": {
        "errors": [
            {
                "code": "error.forbidden",
                "message": "Unathorized to view"
            }
        ]
    },
    "meta": []
}
```

Ensure that you include the proper authentication with your call.

##Unauthorized to View Workspace

A call attempting to view a workspace without the proper permissions returns the following response:

```
{
    "status": false,
    "response": {
        "errors": [
            {
                "code": "error.forbidden",
                "message": "Unathorized to view workspace"
            }
        ]
    },
    "meta": []
}
```

Ensure that you include the proper authentication with your call.

##Workspace Does Not Exist

A call attempting to view a non-existant workflow returns the following response:

```
{
    "status": false,
    "response": {
        "errors": [
            {
                "code": "error.forbidden",
                "message": "Unathorized to view workspace"
            }
        ]
    },
    "meta": []
}
```

Ensure that you include the proper authentication with your call.