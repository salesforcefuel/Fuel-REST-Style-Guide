This method adds a tag value to an author object within your account. You can add a single tag in a call or pass a array of multiple tag values

##Resource

	/v3/authors/{authorId}/tags

##HTTP Method

	POST

##Request Parameters

	*authorId* - Integer value indicating the ID of the specific author (required)

##Request Parameters Example

	POST /v3/authors/{authorId}/tags

##JSON Parameters

	*value* - string value including the tag value to apply to the author

##Sample Request

The call below passes a single tag to the author.
```
POST /v3/authors/1/tags

Content-Type:application/json
{
"value":"vino"
}
```

The call below passes an array of tags to the author.
```
POST /v3/authors/1/tags
[{
  "value": "Some Tag Value 1"
},
{
  "value": "Some Tag Value 2"
},
{
  "value": "Some Tag Value 3"
}]
```

##Sample Response

A successful call returns a 201 code with a Location header for the location of the new tag and an ID value. If you pass an array of tags, that response will include a Location header and an array of IDs for the tags.
```
[
  {
    "id": "154"
  },
  {
    "id": "155"
  },
  {
    "id": "156"
  }
]
```

A call including an invalid JSON object will return a 400 code. Ensure you correctly formed the JSON object.

A call referencing an invalid author ID will return a 404 code. Ensure you referenced the correct author value.

A duplicate tag returns a 409 code. Ensure you include a unique tag value in your call.