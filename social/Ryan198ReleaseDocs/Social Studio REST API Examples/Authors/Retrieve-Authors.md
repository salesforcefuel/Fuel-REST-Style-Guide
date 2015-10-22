This method retrieves the specified author from a workspace.

##Resource

	/v3/authors/{id}

##HTTP method

	GET

##Request Parameters

	*id* - string value indicating the author of a post (required)

##Request Parameter Example

	GET /v3/authors/{id}

##Sample Request

	GET /v3/authors/{id}

##Sample Response

A successful call returns the following response:
```
{
    "data": [
        {
            "id": "2184",
            "title": "R6APITestUser1",
            "externalId": "429245766",
            "externalLegacyId": null,
            "authorFullName": "API 1 APIQE อาหารสั",
            "avatar": "http://pbs.twimg.com/profile_images/1815149549/b-410745-animated_dog_normal.jpg",
            "authorTags": [
                {
                    "id": "13434",
                    "value": "Sample tag"
                }
            ],
            "authorComments": [
                {
                    "id": "454545",
                    "value": "Sample note"
                }
            ],
            "bio": "Sample bioั",
            "verified": false,
            "authorData": {
                "blogId": "62550515"
            }
        }
    ],
    "meta": {
        "totalCount": 1
    }
}
```

    *id* - string value indicating author
    *title* - string value indicating author title
    *externalid* - string value indicating ID for author on external platform
    *externalLegacyId* - string value indicating any other external platform identifier for author
    *authorFullName* - string value indicating any available full name for author
    *avatar* - string value indicating URL for avatar image file
    *authorTags* - array containing ID and value pairs for tags associated with author
    *authorComments* - array containing ID and value pairs for comments associated with author
    *bio* - string value containing bio information for author from external platform
    *verified* - boolean value indicating verified status for Twitter
    *authorData* - array containing additional information on author, such as blogID

A call referencing a nonexistant author returns a 404 error.

A call that encounters an internal error while retrieving the author returns a 500 error.