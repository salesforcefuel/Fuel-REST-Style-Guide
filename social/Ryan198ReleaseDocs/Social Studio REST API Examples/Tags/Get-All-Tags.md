This method retrieves all tags within an account.

##Resource

	/v3/Tags

##HTTP Method

	GET

##Request Parameters

	None

##Request Parameters Example

	GET /v3/Tags

##Query Parameters

	*tag* - string value indicating type of tag (required):
		*author* - return author tags
	*limit* - integer value indicating number of results to return (defaluts to 1000)
	*offset* - integer value indicating result to start with in returned results
	*q* - string value including search string query (minimum of three characters), indicates return of exact match on tag value
	*sinceDate* - timestamp value indicating a filter on a collection of values created on or after the specified date. This value supports milliseconds since epoch and ISO 8601 datetime (which can be fully or partially URL encoded, such as "2014%2D02%2D03").

##Sample Request

	GET /v3/Tags?=author

##Sample Response

A successful call returns the following response:
```
{
  "data" : [
    {
      "id": "0",
      "link": "https://stg1-api/socialcloud/v3/posts/1352570476",
      "updated": "2014-10-31T12:44:43Z",
      "title": "Author Tag",
      "createdBy": {
        "id": "2999",
        "link": "https://stg1-api/socialcloud/v3/users/2999",
        "updated": "2014-11-03T14:40:55Z",
        "title": "user1",
        "email": "user1@example.org",
        "avatarURL": null
      },
      "content": {
        "value": "vino"
      }
    }
  ],
  "meta" : {
    "totalCount" : 1
  }
}

```

  **data - an array of tag objects
    *id* - integer value indicating the unique ID for a tag
    *link* - string value indicating the URL for the tag
    *updated* - timestamp value indicating the last time the system updated the tag
    *title* - string value including the name of the tag
    *createdBy* - object including information on the creator of the tag
      *id* - integer value indicating the unique ID for the user that created the tag
      *link* - string value including the URL for the user that created the tag
      *updated* - timestamp value indicating the last time the system updated the user
      *title* - string value indicating the name of the user
      *email* - string value indicating the email address of the user
      *avatarURL* - string value indicating the URL for the avatar image file
  *content* - array of tag values
    *value* - string value containing text for tag

A call with any invalid query parameters returns a 400 code.

A internal error during creation returns a 500 Internal Server Error. Try your create call again at a later time.