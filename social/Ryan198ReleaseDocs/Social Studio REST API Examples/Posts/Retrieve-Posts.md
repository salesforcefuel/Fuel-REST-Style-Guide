This method retrieves post data from available broad listening topic profiles and social accounts.

##Resource
	
	v3/posts

##HTTP Method

	GET

##Request Parameters
	
	*topics* - string value containing comma-delimited list of topic profile IDs to include in call (required)
	*limit* - integer value indicating number of posts to return in the call (defaults to 25, accepts values from 1 to 1000)
	*sinceId* - integer value indicating ID of post to start retrieve. This parameter allows only posts created after the identified post.
	*beforeId* - integer value indicating ID of post to start retrieve. This parameter allows only posts created before and including the identified post.
	*startDate* - timestamp value indicating the the start date for the filter. This parameter allows only those posts published to the social media channel on or after the given date, based on the *updated* attribute for the post (defaults to 24 hours before call occurs).
	*endDate* - timestamp value indicating the the end date for the filter. This parameter allows only those posts published to the social media channel on or before the given date, based on the *updated* attribute for the post (defaults to current time).
	*mediaTypes* - string value containing comma-delimited list of media type IDs to include in call (defaults to all applicable media types including in the specified topic profiles)
	*extendedMediaTypes* - string value containing comma-delimited list of extended media type IDs to include in call (defaults to all applicable extended media types including in the specified topic profiles)
	*includeWorkflow* - boolean value indicates whether to include workflow with the returned posts (defaults to false)
	*includeSpam* - boolean value indicating whether to include posts flagged as spame by the Salesforce Marketing Cloud (defaults to false)
	*includeAnchors* - boolean value indicating whether to include anchor tags in content. A *true* value indicates the call returns links as HTML anchor tags within the returned post content. A *false* value returns plain text (defaults to false).
	*highlight* - boolean value indicating whether the call highlights keywords. A *true* value indicating highlighted keywords from the topic profile configuration in the post content for use when presented in a web page. A *false* value returns plain text (defaults to false).
	*keywords* - string value containing a comma-delimited list of keywords to use when returning only posts containing those values. This parameter includes up to 50 values and ignores duplicates. 
	*sortBy* - string values indicating how call sorts the response:
		*publishedDate* - sort by published date in descending order
		*publishedDate-ascending* - sort by published date in ascending order
		*blogPostId* - sort by post object ID in descending order (default)
		*blogPostId-ascending* - sort by post object ID in ascending order
		*rankBM25* - sort by relevance rank based on matched keywork frequency
	*keywordGroups* - string value containing comma-delimited list of filter group IDs used to filter posts associated only with those groups. Defaults to all keyword groups provided in topic profiles from the *topics* parameter.
	*includeSourceFilterMatches* - boolean value indicating whether to include the source filters containing URLs each post matches (defaults to false)
	*regions* - string value containing comma-delimited list of region IDs (defaults to all regions assigned to topics from the *topic parameter)
	*languages* - string value containing comma-delimited list of language IDs (defaults to all languages assigned to topics from the *topic parameter)
	*assignedUser* - string value including a comma-delimited list of users IDs for users within the same client as the calling user
	*engagement* - string value containing comma-delimited list of engagement status IDs to return
	*priority* - integer value indicating priority values to use when returning posts:
		*1* - low
		*2* - medium
		*3* - high
	*classification* - string value containing comma-delimited list of classifications to return
	*eventsSince* - timestamp value used to indicate posts to return after provided value (milliseconds after midnight on 1/1/1970). Adding this parameter includes an HTTP header called Workflow-As-Of-Date that contains current timestamp of call. Use this value to retrieve only workflow events applied since previous method call. This parameter considers only workflow applied within last 30 days of call.
	*unassigned* - boolean value indicating the call returns onlu unassigned posts
	*sentiment* - string value containing comma-delimited list of sentiment IDs used to filter posts:
		*-10*
		*-5*
		*0*
		*5*
		*10*
		*99*
	*authorTags* - string value containing comma-delimited list of author tags used to filter posts	
##Request Parameter Sample

	GET /v3/posts

##Sample Call

The call below returns posts from the specified topic profile:
```
GET /v3/posts?topics=1234
```

The call below returns the latest 50 Twitter posts:
```
GET /v3/posts?topics=1234&mediaTypes=8&limit=50
```

The call below returns the latest 50 Twitter posts since the specified ID
```
GET /v3/posts?topics=1234&mediaTypes=8&limit=50&sinceId=777777
```

##Sample Response
```
{
  "id": "1828477438",
  "title": "Tennis Star visits Malawi",
  "externalId": null,
  "externalLink": "http://www.youtube.com/watch?v=exampleValue",
  "sourceApplication": null,
  "content": "",
  "summaryContent": "",
  "publishedDate": "2015-07-21T10:07:58Z",
  "harvestDate": "2015-07-21T11:23:23Z",
  "languageId": 1,
  "regionId": 249,
  "postStatus": 0,
  "mediaProvider": {
    "id": "2",
    "title": "YouTube",
    "mediaTypeId": 2,
    "extendedMediaType": null
  },
  "source": {
    "id": "2229562169",
    "title": "Tennis Star visits Malawi",
    "externalLink": "youtube.com",
    "language": "en",
    "region": null,
    "tags": [
      {
        "id": "7494",
        "value": "Sample source tag"
      }
    ],
    "comments": [
      {
        "id": "56436",
        "value": "Sample source comment",
        "noteTypeId": "4"
      }
    ]
  },
  "author": {
    "id": "-1",
    "title": "YouTube Channel",
    "externalId": "-1",
    "externalLegacyId": null,
    "authorFullName": "YouTube Channel",
    "avatar": null,
    "authorTags": [
      {
        "id": "5567567",
        "value": "Sample author tag"
      }
    ],
    "authorComments": [
      {
        "id": "556456456",
        "value": "Sample author comment"
      }
    ],
    "bio": null,
    "verified": false
  },
  "parent": null,
  "sentiment": null,
  "postStatusException": null,
  "engagement": 4564,
  "classification": 4,
  "tags": [
    {
      "id": "5466546",
      "value": "Sample tag"
    }
  ],
  "postDynamics": [
    {
      "fieldId": "5",
      "label": "View Count",
      "value": "0"
    },
    {
      "fieldId": "1",
      "label": "Comment Count",
      "value": "0"
    },
    {
      "fieldId": "2",
      "label": "Unique Commenters",
      "value": "0"
    },
    {
      "fieldId": "3",
      "label": "Engagement",
      "value": "0"
    },
    {
      "fieldId": "4",
      "label": "Likes and Votes",
      "value": "0"
    },
    {
      "fieldId": "7",
      "label": "Inbound Links",
      "value": "0"
    },
    {
      "fieldId": "21",
      "label": "Sentiment",
      "value": "0",
      "overridden": "false"
    }
  ],
  "metadata": null,
  "topics": [
    4526
  ],
    "sourceFilterMatches": null,
    "assignedUser": null,
    "comments": [
      {
        "id": "435345",
        "value": "Sample comment",
        "noteTypeId": "0"
      }
    ]
  }
}
```

	*id* - integer value indicating unique indentifier for post object, used to assign and access workflow associated with post
	*link* - string value including URI of post. This link does not currently look up and individual post, so use only as an indentifier with workflow to return workflow values of a specific post.
	*updated* - timestamp value indicating time of last update
	*title* - string value containing description of post
	*externalId* - integer value indicating unique ID for post assigned by original social media channel (such as Facebook or Twitter)
	*externalLink* - string value containing URL of original post
	*sourceApplication* - string value for name of application that created Twitter content
	*content* - string value containing text of original post, including links
	*summaryContent* - string value reserved for internal use (will always return empty)
	*harvestDate* - timestamp value indicating when Social Studio discovered and indexed post
	*languageId* - integer value indicating supported language for post (review Languages route for available IDs)
	*regionId* - integer value indicating region associated with post (review region route for available IDs)
	*postStatus* - integer value indicating post status:
		*0* - normal, active post
		*1* - spam (auto-detected)
		*2* - deleted or hidden post (based on user action)
	*sentiment* - integer value indicating manually assigned sentiment value (requires includeWorkflow=true)
	*postStatusException* - integer value indicating manually assigned post status value (requires includeWorkflow=true)
	*engagement* - integer value indicating state(such as under review or closed) of post (requires includeWorkflow=true)
	*classification* - integer value indicating classification group assigned to post (requires includeWorkflow=true)
	*assignedUSer* - intetger value indicating user assigned to post (requires includeWorkflow=true)
	*priority* - integer value indicating priority assigned to post (requires includeWorkflow=true)
	*tags* - array of tag values attached to post (requires includeWorkflow=true)
	*comments* - array of comment values attached to post (requires includeWorkflow=true)
	*mediaProvider* - object containing information about post within context of original social network:
		*id* - integer value indicating original social network
    	*title* - string value indicating name of original social network
    	*mediaTypeId* - number value indicating type of media
    	*extendedMediaType* - number value indicating type of extended media
	*source* - object containing information about post source used to represent source in Social Studio. Multiple posts may use the same source. Requires includeWorkflow=true.
	    *id* - integer value indicating unique identifier of source
    	*title* - string value containing text describing post
    	*externalLink* - string value containing link to original post
    	*language* - string value containing ISO language code
    	*region* - string value containing region associated with post
    	*tags* - array of string values indicating tags for post
    	*verified* - boolean value indicating whether Twitter verified post
	*author* - object containing information about individual or company that created post (requires includeWorkflow=true)
		*id* - integer value indicating unique identifier for author
    	*title* - string value containing text describing author
    	*externalId* - integer value indicating unique identifier for author on social media channel
    	*externalLegacyId* - integer value indicating unique legacy identifier for author on social media channel
    	*authorFullName* - string value containing full name for author
    	*avatar* - string value containing location for avatar image file
	    *authorTags* - array containing ID and value pairs for tags attached to author
	    *authorComments* - array containing ID and value pairs for comments attached to author
    	*bio* - string value containing author bio information
    	*verified* - boolean value indicating whether Twitter verified author
	*parent* - object containing IDs used by Social Studio and the social media channel to identify parent post
	*postDynamics* - object containing more information about the post (such as number of likes or comments for a post). These numbers change over time and vary from social channel to social channel.
	*metadata* - object containing additional metadata bout the post. This informcation can change over time and vary from social channel to social channel.
	*topics* - object containing information about the topics associated with the post (topics assigned in request parameter)
	*sourceFilterMatches* - object containing the source filter with URLs the post matches
	*parentAuthor* - object containing information on author of parent post for current post. Currently used only for retweeted Twitter posts.