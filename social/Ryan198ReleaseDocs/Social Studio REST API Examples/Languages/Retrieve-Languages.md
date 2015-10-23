This method retreives information about all languages available within an account.

##Resources

	/v3/languages

##HTTP Method

	GET

##Request Parameters

	*limit* - integer value indicating number of results to return (defaults to 1000). This method does not return any deleted comments.
	*offset* - integer value indicating result to start with (defaults to 0)

##Request Parameter Example

	GET /v3/languages

##Sample Request
```
	GET /v3/languages
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
    {
      "id": "2",
      "title": "French",
      "code": "fr"
    },
    {
      "id": "3",
      "title": "Spanish",
      "code": "es"
    },
    ...
  ],
  "meta": {
    "totalCount": 28
  }
}
```

	*id* - integer value identifying the language
	*title* - string value containing the English-language name for the language
	*code* - string value containing the ISO language code for the language