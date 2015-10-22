This method retrieves a single social propertie from those available for the user to access. This object contains information about a managed account topic profile and associated external user account. The socialPropertyId value equals the managed account topic filter ID.

##Resource

	v3/socialProperties

##HTTP Method

	GET

##Request Parameters

	*socialPropertyId*

##Request Parameter Sample

	GET	/v3/socialProperties/{socialPropertyId}

##Sample Request
```
GET /v3/socialProperties/121218
```

##Sample Response
```
{
  "data": [
    {
         "id": "121218",
         "displayName": "Jane's test software",
         "pageUrl": "https://facebook.com/pages/Janes-test-softwar/128544450650919",
         "networkTypeId": 4,
         "avatarUrl": "https://fbcdn-profile-a.akamaihd.net/hprofile-ak-xaf1/v/t1.0-1/c151.34.422.422/s50x50/552488_128545593954160_2159838340_n.jpg?oh=cb08f9353545f1bb437f96022466a235&oe=563DA948&__gda__=1448168411_3a661fa573372b8fc3b31058feeb6c8c",
         "slug": "pages/Janes-test-software/128544450650919",
         "valid": true
      },
  ],
  "meta": {
    "totalCount": 1
  }
}
```

	*data* - array of information on returned social properties:
		*id* - string value indicating unique ID for social property
		*displayName* - string value containing name of social property
		*pageUrl* - string value containing URL of social property on social network
		*networkTypeId* - integer value indicating social network
		*avatarUrl* - string value containing location of avatar image file
		*slug* - string value containing slug for social property
		*valid* - boolean property indicating whether social media account remains active and valid