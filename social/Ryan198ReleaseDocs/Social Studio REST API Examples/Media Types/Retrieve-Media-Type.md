This method retrieves a single media types from the account based on the supplied ID.

##Resources

	/v3/mediaTypes

##HTTP Method

	GET

##Request Parameters

	*mediaTypeId* - integer value indicating media type to retrieve

##Request Parameter Example

	GET	/v3/mediaTypes

##Sample Request
```
GET /v3/mediaTypes/1
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
    }
  ],
  "meta": {
    "totalCount": 1
  }
}
```

	*id* - integer value indicating unique identifier of media type
	*updated* - timestamp value indicating data and time of last updated
	*title* - string value indicating description of media type
	*isVisbile* - boolean value indicating visibility of media type in account
	*classificationId* - integer value indicating unique identifier of media type classification
	*classificationType* - string value indicating description of media type classification