This method retrieves social properties the user can access. This object contains information about a managed account topic profile and associated external user account.

##Resource

	v3/socialProperties

##HTTP Method

	GET

##Request Parameters

	*view* - string value including comma-separated list of properties to return (defaults to OWNED;(only those properties created by requesting user))
		*OWNED* - all social properties created by requesting user
		*SHARED* - all social properties shared with and not owned by requesting user
	*registrationId* - integer value indicating return of social properties with specified registration ID
	*types* - integer value indicating return of social properties with specified registration types
	*socialNetworkId* - integer value indicating return of social properties with specified social network ID
	*workspaceGroupId* - string value indicating return of social properties within specified workspace group
	*limit* - integer value indicating number of results to return (defaluts to 25)
	*offset* - integer value indicating result to start with in returned results
	*status* - string value including comma-separated list of integers indicating return of social properties with specified status values
	*invalidAccountsFirst* - boolean value indicating return of *invalid* values first, then *OK* and *new* values (defaults to false)
	*orderBy* - string value indicating fields used to sort returned social properties:
		*title* - string value describing post
		*creator* - string value including creator of post
		*visibility* - string value indicating visibility of post*
		*status* - integer value indicating status of post
	*q* - string value including search string query (minimum of three characters), indicates return of social properties with partial case-insensitive match on topic title or creator name
	*ids* - string value indicating comma-delimited list of valid social proeprty IDs to return. Only returns visible social properties. The call returns a 404 error if no social properties are available. The call normalizes duplicate values and ignores all other query parameters.

##Request Parameter Sample

	GET	/socialProperties

##Sample Request
```
GET /v3/socialProperties?socialNetworkId=4
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
            {
         "id": "111819",
         "displayName": "I Heart CBC NB",
         "pageUrl": "https://facebook.com/pages/I-Love-CBC-NB/376189652448432",
         "networkTypeId": 4,
         "avatarUrl": "https://fbcdn-profile-a.akamaihd.net/hprofile-ak-xfa1/v/t1.0-2/p50x50/305074_380514875349292_382752874_n.jpg?oh=02eb66e27be49c4d3a99576b4997493b&oe=5651FCB9&__gda__=1447361104_cbbb529d940f10185f2877dd306967de",
         "slug": "pages/I-Love-CBC-NB/376189652448432",
         "valid": true
      }
  ],
  "meta": {
    "totalCount": 2
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
