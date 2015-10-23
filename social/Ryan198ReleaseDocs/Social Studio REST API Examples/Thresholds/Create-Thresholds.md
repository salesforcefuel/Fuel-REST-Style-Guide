This method creates a threshold within an account.

##Resource

	/v2/thresholds

##HTTP Resource

	POST

##Request Parameters

	None

##Request Parameters Example

	POST /v2/thresholds

##JSON Parameters

No values can equal zero.

	*title* - string value including name of threshold
	*description* - string value including description of threshold
	*type* - string value indicating type of threshold
		*absolute* - string value indicating numeric value threshold (must be a positive value)
		*percentile* - string value indicating percentage of current value threshold (can be positive or negative value not exceeding -100, using negative values to monitor decreases)
	*value* - integer value indicating value for threshold
	*timespan* - object including data on threshold duration (cannot exceed 7 days)
		*scale* - string value indicating unit of time
			*days*
			*hours*
		*measure* - integer value indicating number of days or hours as applicable
	*emailFrequency* - integer value indicates minutes between email messages
	*notifications* - array of notification objects
		*type* - string value indicating type of notifiction
			*email*
		*address* - string value indicating address for use with notification
		*subject* - string value indicating text of notification
		*sender* - string value indicating name of sender of notification

#Sample Request
```
POST /v2/thresholds
{
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
        "type": "email",
        "address": <address>,
        "subject": <subject text>,
        "sender": <sender name>
    }]
}

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