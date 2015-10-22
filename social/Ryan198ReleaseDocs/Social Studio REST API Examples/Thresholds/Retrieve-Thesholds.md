This method retrieves all thresholds created in the same tenant as the user.

##Resource

	/v2/thresholds

##HTTP Resource

	GET

##Request Parameters

	None

##Request Parameters Example

	GET /v2/thresholds

##Sample Request
```
GET /v2/thresholds
```

##Sample Responses

The response includes an array of threshold objects:

```
{
    "id": <id>,
    "link": "https://<api-server>/socialcloud/v2/thresholds/<threshold-id>",
    "created": <created date>,
    "createdBy": {
        "id": <user id>,
        "clientId": <client id>,
        "clientName": <client name>,
        "username": <username>,
        "email": <email>
    },
    "updated": <last update date>,
    "updatedBy": {
        "id": <user id>,
        "clientId": <client id>,
        "clientName": <client name>,
        "username": <username>,
        "email": <email>
    },
    "status": "running|suspended",
    "lastFired": <last fired date>,
    "title": <title>,
    "description": <description>,
    "type": "absolute|percentile",
    "value": <value of threshold>,
    "timespan": {
        "scale": "days|hours"
        "measure": <units of time>
    },
    "emailFrequency": <frequency in minutes>,
    "notifications": [{
        "type":"email",
        "address": <address>,
        "subject": <subject text>,
        "sender": <sender name>
    }]
}
```

    *id* - integer value including unique identifier for threshold
    *link- string value including URL to threshold object
    *created* - timestamp value indicating date of creation for threshold
    *createdBy* - object containing information about user who created threshold:
        *id* - integer value including unique identifier for user
        *clientId* - integer value indicating client ID for specific user
        *clientName* - string value including name of user
        *username* - string value including network username for user
        *email* - string value including email address for user
    *updated* - timestamp value indicating date of last update for threshold
    *updatedBy* - object containing information about user who last updated threshold:
        *id* - integer value including unique identifier for user
        *clientId* - integer value indicating client ID for specific user
        *clientName* - string value including name of user
        *username* - string value including network username for user
        *email* - string value including email address for user
    *status* - string value indicating current operational status for threshold
        *running* - string value indicating active threshold
        *suspended* - string value indicating non-active threshold
    *lastFired* - timestamp value indicating time the threshold last performed
    *title* - string value including name of threshold
    *description* - string value including text describing threshold
    *type* - string value indicating type of threshold:
        *absolute* - string value indicating threshold uses a specific numeric value
        *percentile*  - string value indicating threshold uses a percentile value based on the overall target
    *value* - integer value indicsting limit for threshold
    *timespan* - object including information for how long the threshold operates:
        *scale* - string value indicating unit of measurement for timespan:
            *days*
            *hours*
        *measure* - integer value indicating the number of units including in the timespan
    *emailFrequency* - integer value indicating frequency of email sends (measured in minutes)
    *notifications* - object indicating type of messaging user by threshold:
        *type* - string value indicating type of message used:
            *email*
        *address* - string value including address used in notification
        *subject* - string value including text of subject line
        *sender* - string value including sender information