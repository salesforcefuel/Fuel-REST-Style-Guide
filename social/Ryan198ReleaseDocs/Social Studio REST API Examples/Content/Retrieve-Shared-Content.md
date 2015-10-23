This method retrieves content available for use within a workspace.

##Resource

	/v1/clips/

##HTTP Method

	GET

##Request Parameters

  None

##Query Parameters

	*workspace* - string value indicating workspace from which to retrieve content (required)
	*filter* - string value indicating which content to retrieve:
		*all* - any content (default)
		*owner* - any content owned by a specific owner
		*shared* - any content shared for use
	*include* - string value requesting additional information:
		*metrics* - analytics information for specified content
	*sort* - string value indicating order to display retrieved content:
		*created* - sort by created date (default)
		*avg_engagement* - sort by average number of engagement
	*direction* - string value indicating display direction for retrieved content:
		*desc* - descending order (default)
		*asc* - ascending order
	*page* - integer value indicating which page to display from retreived data (defaults to 1)
	*perpage* - integer value indicating how many results to include in a page (defaults to 10)

##Request Parameter Example

	GET	/v1/clips

##Sample Request

The call below retrieves all clips from the specified workplace with analytics data:
```
GET /v1/clips?workspace=584d3ad3-2f7b-11e3-b8e3-168170973bd5&filter=all&include=metrics
```

The call below retrieves a clip by ID:
```
GET v1/clips/35543aba-18b2-4995-bb76-ea1132fe544a
```

##Sample Response

A successful call requesting all clips with analytics data returns the following response:
```
{
    "status": true,
    "response": [
        {
           "id": "35543aba-18b2-4995-bb76-ea1132fe544a",
           "source_type": "post",
           "source_id": "93023aba-18b2-4995-bb76-ea1132fe544a",
           "organization_id": "10567",
           "archived": 0,
           "deleted": 0,
           "message": "Post message",
           "description": "Clip comment",
           "start_date": null,
           "end_date": null,
           "created": "2014-02-02 11:00:00",
           "updated": "2014-02-03 11:00:00",
           "assets": [
               {
                 "url": "https://d2ee3wvl22m8i7.cloudfront.net/_blue.jpg",
                 "type": "2",
                 "metadata": null
               }
           ],
           "owner_workspace":
           {
              "id": "75443f9c-349b-4bfa-a124-b188d4a8719f",
              "owner": "1",
              "name": "Buddy - The Dog",
              "logo": null
           },
           "shared_workspace_count": 0,
           "shared_workspaces": [
                {
                  "id": "adlskasdaf-dsafada",
                  "name": "workspace 1",
                  "logo": "http://image.jpg"
                },
                {
                  "id": "adlskasdaf-dsafada",
                  "name": "workspace 2",
                  "logo": "http://image.jpg"
                 }
           ],
           "post_count": 19,
           "metrics": {
                 "engagement": 354,
                 "average_engagement": 177,
                 "engagement_rate": {
                    "facebook": 1.4,
                    "twitter": 1.5
                 }
           }
        },
        {
            ...
        },
        ...
    ]
    "meta": {
        "total": 5,
        "perpage": 10,
        "current": 1,
        "prev": "",
        "next": "/clips?page=2&perpage=10"
    }
}
```

A successful call for a specific piece of content returns the following response:
```
{
    "status": true,
    "response": {
           "id": "35543aba-18b2-4995-bb76-ea1132fe544a",
           "source_type": "post",
           "source_id": "93023aba-18b2-4995-bb76-ea1132fe544a",
           "organization_id": "10567",
           "archived": 0,
           "deleted": 0,
           "message": "Post message",
           "description": "Clip comment",
           "start_date": null,
           "end_date": null,
           "created": "2014-02-02 11:00:00",
           "updated": "2014-02-03 11:00:00",
           "assets": [
               {
                 "url": "https://d2ee3wvl22m8i7.cloudfront.net/_blue.jpg",
                 "type": "2",
                 "metadata": null
               }
           ],
           "owner_workspace":
           {
              "id": "75443f9c-349b-4bfa-a124-b188d4a8719f",
              "owner": "1",
              "name": "Buddy - The Dog",
              "logo": null
           },
           "shared_workspace_count": 0,
           "shared_workspaces": [
                {
                  "id": "adlskasdaf-dsafada",
                  "name": "workspace 1",
                  "logo": "http://image.jpg"
                },
                {
                  "id": "adlskasdaf-dsafada",
                  "name": "workspace 2",
                  "logo": "http://image.jpg"
                 }
           ],
           "post_count": 19,
           "metrics": {
                 "engagement": 354,
                 "average_engagement": 177,
                 "engagement_rate": {
                    "facebook": 1.4,
                    "twitter": 1.5
                 }
           }
    },
    "meta": []
}
```

    *status* - string value indicating success of call
    *response* - array of information related to retrieved content:
        *id* - string value indicating ID of content
        *source_type* - string value indicating method of creation for content
        *source_id* - string value containing ID of content source
        *organizationId* - sting value containing ID of organization
        *archived* - integer value indicating number of archived posts 
        *deleted* - integer value indicating number of deleted posts 
        *message* - string value including content message
        *description* - string value including description of content
        *start_date* - timestamp value including start date for content
        *end* - timestamp value including end date for content
        *created* - timestamp value including creation date for content
        *updated* - timestamp value including update date for content
        *assets* - array value including information on content
          *url* - string value including URL for content assets
          *type* - integer value indicating content type (NEED CONTENT TYPE HERE)
          *metadata* - addtional date for content
        *owner_workspace* - array value including data on workspacing owning content
          *id* - string value including ID for owner workspace
          *owner* - integer value indicating owner
          *name* - string value including name of content in workspace
          *logo* - string value indicating logo assocaited with content
        *shared_workspace_count* - integer value indicating number of workspaces sharing content
          *shared_workspaces* - array including information on workspaces sharing content
            *id* - string value indicating ID of workspace sharing content
            *name* - string value including name of workspace sharing content
            *logo* - string value including location of logo image file
        *post_count* - integer value indicating number of times post used
        *metrics* - array of information on content
          *engagement* - integer value including number of engagements
          *average_engagement* - integer value including average number of engagement
            *engagement_rate* - array of engagement information by social network
              *facebook* - integer value including engagement rate on Facebook
              *twitter* - integer value including engagement rate on Twitter