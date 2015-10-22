This method returns the history of activities within the workflow associated with a specified post. Use this information to extract performance indicators when treating social media posts as actionable support or community events.

##Resources

	v3/posts

##HTTP Method

	GET

##Request Parameters

	*is* - integer value indicating unique ID for post

##Request Parameter Example

	GET	v3/posts/{id}/workflow

##Sample Request
```
GET	v3/posts/1828477438/workflow
```

##Sample Response
```
{
    "data": [
        {
            "id": "1828477438",
            "title": "Tennis Star visits Malawi",
            "externalId": null,
            "externalLink": "http://www.youtube.com/watch?v=nOw9cDh83Ks",
            "sourceApplication": null,
            "content": "",
            "summaryContent": "",
            "publishedDate": "2015-07-21T10:07:58Z",
            "harvestDate": "2015-07-21T11:23:23Z",
            "languageId": 1,
            "language": "en",
            "regionId": 249,
            "region": null,
            "postStatus": 0,
            "mediaProvider": {
                "id": "2",
                "title": "YouTube",
                "mediaTypeId": 2,
                "extendedMediaType": null
            },
            "source": {
                "id": "2229562169",
                "title": "Roger Federer visit Malawi - Federer Foundatio'",
                "externalLink": "youtube.com",
                "language": "en",
                "region": null
            },
            "author": {
                "id": "-1",
                "title": "YouTube Channel",
                "externalId": "-1",
                "externalLegacyId": null,
                "authorFullName": "YouTube Channel",
                "avatar": null,
                "tags": null,
                "bio": null,
                "verified": false
            },
            "parent": null,
            "sentiment": [
                {
                    "topicId": 4526,
                    "value": 0,
                    "overridden": false
                }
            ],
            "workflow": [],
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
            "sourceFilterMatches": null
        },
        {
            "id": "1828401832",
            "title": "Jeremy Chardy v Paul Henri-Mathieu skistar swedish open 2015",
            "externalId": null,
            "externalLink": "http://www.youtube.com/watch?v=U1pEVzAOfFc",
            "sourceApplication": null,
            "content": “Soccer player scores goal,
            "summaryContent": "Great kick!",
            "publishedDate": "2015-07-21T09:47:04Z",
            "harvestDate": "2015-07-21T11:15:14Z",
            "languageId": 1,
            "language": "en",
            "regionId": 249,
            "region": null,
            "postStatus": 0,
            "mediaProvider": {
                "id": "2",
                "title": "YouTube",
                "mediaTypeId": 2,
                "extendedMediaType": null
            },
            "source": {
                "id": "2229560153",
                "title": "Jeremy Chardy v Paul Henri-Mathieu skistar swedish open 2015",
                "externalLink": "youtube.com",
                "language": "en",
                "region": null
            },
            "author": {
                "id": "-1",
                "title": "swedish open 2015",
                "externalId": "-1",
                "externalLegacyId": null,
                "authorFullName": "swedish open 2015",
                "avatar": null,
                "tags": null,
                "bio": null,
                "verified": false
            },
            "parent": null,
            "sentiment": [
                {
                    "topicId": 4526,
                    "value": 10,
                    "overridden": false
                }
            ],
            "workflow": [],
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
                    "value": "10",
                    "overridden": "false"
                }
            ],
            "metadata": null,
            "topics": [
                4526
            ],
            "sourceFilterMatches": null
        }
    ],
    "meta": {
        "totalCount": 2
    }
}
```

	*id* - integer value indicating unique indentifier for post object, used to assign and access workflow associated with post
	*title* - string value containing description of post
	*externalId* - integer value indicating unique ID for post assigned by original social media channel (such as Facebook or Twitter)
	*externalLink* - string value containing URL of original post
	*sourceApplication* - string value for name of application that created Twitter content
	*content* - string value containing text of original post, including links
	*summaryContent* - string value reserved for internal use (will always return empty)
	*harvestDate* - timestamp value indicating when Social Studio discovered and indexed post
	*languageId* - integer value indicating supported language for post (review Languages route for available IDs)
	*language* - string value indicating ISO language code
	*regionId* - integer value indicating region associated with post (review region route for available IDs)
	*region* - string value indicating region associated with post
	*postStatus* - integer value indicating post status:
		*0* - normal, active post
		*1* - spam (auto-detected)
		*2* - deleted or hidden post (based on user action)
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
	*sentiment* - object containing sentiment information for topic
		*topicId* - integer value identifying topic
		*value* - integer value indicating sentiment
		*overridden* - boolean value indicating overriden sentiment value
	*workflow* - object containing information on workflow performed on post.
	*postDynamics* - object containing more information about the post (such as number of likes or comments for a post). These numbers change over time and vary from social channel to social channel.