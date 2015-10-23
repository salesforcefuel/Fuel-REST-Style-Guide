This method retreives information about all languages available within an account.

##Resources

	/v3/languages

##HTTP Method

	GET

##Request Parameters

	*id* - integer value indicating the language to retrieve
  
##Request Parameter Example

	GET /v3/languages{id}

##Sample Request
```
	GET /v3/languages/1
```

##Sample Response

A successful call returns the following response:

```
{
  "data": [
    {
      "id": "1",
      "title": "English",
      "code": "en"
    },
  ],
  "meta": {
    "totalCount": 1
  }
}
```

	*id* - integer value identifying the language
	*title* - string value containing the English-language name for the language
	*code* - string value containing the ISO language code for the language