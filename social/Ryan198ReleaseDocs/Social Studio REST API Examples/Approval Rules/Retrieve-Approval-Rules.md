This method retrieves any rules included in a single approval flow.

##Resource

    /v1/approvalprerequisites

##HTTP method

	GET

##Request Parameters

	*approvalflow* - ID for the approval flow (required)
	*hydrate=argument - indicates that the call should return related entity information instead of string or integer IDs 

##Request Parameter Examples

	GET /v1/approvalprerequisites/{workflowId}

##Sample Request

```
GET {HOST}/v1/approvalprerequisites/46e66860-25fe-11e3-b1a1-168170973bd5
```

```
GET {HOST}/v1/approvalprerequisites/46e66860-25fe-11e3-b1a1-168170973bd5&hydrate=argument
```

##Sample Response

A successful call returns the following response:
```
{
    "status": true,
    "response": {
        "items": [
            {
                "criteria": "submitter",
                "operator": "equals",
                "argument": 123123
            },
            {
                "criteria": "social account",
                "operator": "equals",
                "argument": 83967
            },
            {
                "criteria": "social account",
                "operator": "equals",
                "argument": 84975
            }
        ],
        "query": "(1 AND 2) OR ( 1 AND 3 )"
    },
    "meta": []
}
```

A successful call including the hydrate argument returns the following response:
```
{
    "status": true,
    "response": {
        "items": [
            {
                "criteria": "submitter",
                "operator": "equals",
                "argument": {
                    "id": 7664,
                    "email": "qzhen@example.com",
                    "title": "Qzhen_10100",
                    "avatar_url": null,
                    "timezone": "GMT",
                    "enabled": true,
                    "updated": "2014-02-04T15:50:42+0000",
                    "organization_id": 10100,
                    "roles": 1
                }
            },
            {
                "criteria": "social account",
                "operator": "in",
                "argument": [
                    {
                        "name": "Exercise_Your_Voting_Right",
                        "id": "541a6b23-21ff-4c2c-9ed0-ca81da98d71d",
                        "network": "Facebook",
                        "asset": "519296421491495",
                        "socialaccount": 94093,
                        "tokenStatus": 1,
                        "metadata": {
                            "pageLogo": "https://fbcdn-profile-a.akamaihd.net/static-ak/rsrc.php/v2/yg/r/LjGkeBM0ISt.png",
                            "provider": "FACEBOOK",
                            "userName": "/Exercise_Your_Voting_Right/519296421491495"
                        }
                    },
                    {
                        "name": "Example Page",
                        "id": "3a65a221-c16e-479b-8430-57b46fcb21f2",
                        "network": "Facebook",
                        "asset": "407001072724791",
                        "socialaccount": 94268,
                        "tokenStatus": 1,
                        "metadata": {
                            "pageLogo": "https://fbcdn-profile-a.akamaihd.net/static-ak/rsrc.php/v2/yg/r/LjGkeBM0ISt.png",
                            "provider": "FACEBOOK",
                            "userName": "/Chris-Dev-Page/407001072724791"
                        }
                    }
                ]
            },
            {
                "criteria": "social account",
                    "operator": "equals",
                    "argument": {
                        "id": "83967",
                        "link": "https://stg3-api.dev.ca1.sfmc.co/socialcloud/v2/socialProperties/83967",
                        "updated": "2015-04-20T14:45:35Z",
                        "title": "Ana-192",
                        "topic": {
                            "id": "83967",
                            "link": "https://stg3-api.dev.ca1.sfmc.co/socialcloud/v2/topics/83967",
                            "updated": "2015-02-19T17:06:49Z",
                            "title": "Ana-192",
                            "createdDate": "2015-02-19T17:06:49Z"
                        },
                        "creator": {
                            "id": "79798023",
                            "link": "https://stg3-api.dev.ca1.sfmc.co/socialcloud/v2/users/79798023",
                            "updated": "2015-04-20T14:45:35Z",
                            "title": "Hiren Gosalia",
                            "email": "hgosalia@salesforce.com",
                            "avatarURL": null
                        },
                        "projects": [],
                        "registration": {
                            "id": "16243",
                            "link": "https://stg3-api.dev.ca1.sfmc.co/socialcloud/v2/socialAccounts/16243",
                            "updated": null,
                            "title": "Mansi SFDC",
                            "lastRefreshedTime": null
                        },
                        "lastValidatedTime": null,
                        "avatar": "https://media.licdn.com/mpr/mpr/p/7/005/086/041/07b736a.png",
                        "usedBySalesforce": "false",
                        "visibility": "private",
                        "uniqueName": "ana-192",
                        "realName": "Mansi SFDC",
                        "socialNetwork": {
                            "id": "3880369",
                            "name": "LinkedIn Page",
                            "type": 25
                        },
                        "status": 0,
                        "tokens": {
                            "tokenStatusId": 0,
                            "tokenStatusLastUpdate": null
                        }
                    }
                }
            }
        ],
        "query": "1 AND ( 2 OR 3 )"
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
             *query* - string values indicating AND or OR for query with supplied criteria

The information provided with the hydrate argument varies depending on the included entities.

A call that cannot find the indicated approval flow returns the following response:
```{
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

A call that references an unauthorized approval flow returns the following response:
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
