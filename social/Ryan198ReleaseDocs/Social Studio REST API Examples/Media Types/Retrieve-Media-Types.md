This method retrieves a collection of media types from the account based on supplied parameters.

##Resources

	/v3/mediaTypes

##HTTP Method

	GET

##Request Parameters

	*private* - boolean value indicating a return of only private media tyoes (defaults to false)
	*classificationIds* - string value containing comma-delimited list of media type classification IDs. This parameter returns media types belonging to the specified classifications. When supplying this value, call will ignore *private* parameter and return all results associated with supplied classification IDs.
	*limit* - integer value indicating number of results to return (defaluts to 1000)
	*offset* - integer value indicating result to start with in returned results

##Request Parameter Example

	GET	/v3/mediaTypes

##Sample Request
```
GET /v3/mediaTypes/private=true&classificationIds=1,3
```

##Sample Response
```
{
  "data": [
    {
      "id": "1",
      "title": "Blogs",
      "isVisible": true,
      "classificationId": "1",
      "classificationType": "Broad Listening"
    },
    {
      "id": "2",
      "title": "Videos",
      "isVisible": true,
      "classificationId": "1",
      "classificationType": "Broad Listening"
    },
    ...
  ],
  "meta": {
    "totalCount": 12
  }
}
```

	*id* - integer value indicating unique identifier of media type
	*updated* - timestamp value indicating data and time of last updated
	*title* - string value indicating description of media type
	*isVisbile* - boolean value indicating visibility of media type in account
	*classificationId* - integer value indicating unique identifier of media type classification
	*classificationType* - string value indicating description of media type classification