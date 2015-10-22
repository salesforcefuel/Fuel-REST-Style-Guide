This method returns all commments for a specified author.

##Resource

  /v3/authors/{id}/comments

##HTTP Method

	GET

##Request Parameters

	*id* - string value indicating the author of a post (required)
	*limit* - integer value indicating number of results to return (defaults to 25). This method does not return any deleted comments.
	*offset* - integer value indicating result to start with (defaults to 0)

##Request Parameter Example

	GET /v3/authors/{id}/comments

##Sample Request

	GET /v3/authors/{id}/comments

##Sample Request

A successful call returns the following response:
```
{
  "data" : [
    {
      "id": "2751",
      "authorId": 53,
      "value": "i heart talk radio",
      "deleted": null,
      "created":       {
         "userId": 26341,
         "clientId": 11084,
         "name": "APIQECLIENT1USER1",
         "date": "2015-07-27T13:53:48Z"
      }
   }
  ],
  "meta" : {
    "totalCount" : 1 
  }
}
``` 

  *data* - array of information on comment
    *id* - string value identifying comment
    *authorId* - string value identifying author of comment
    *value* - string value containing text of comment
    *deleted* - string value indicating a deleted comment
    *created* - array of information about comment creation
      *userId* - string value of user ID for comment within system
      *clientId* - string value of client ID for comment within system
      *name* - string value of comment within system
      *date* - timestamp value of creation within system

A call referencing a nonexistant author returns a 404 error.

A call that encounters an internal error while retrieving the author returns a 500 error.