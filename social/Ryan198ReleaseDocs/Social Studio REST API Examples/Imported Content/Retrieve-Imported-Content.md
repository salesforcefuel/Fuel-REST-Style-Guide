This method retrieves posts created by a social network and imported into a workspace.

##Resource

	/v1/importedposts

##HTTP Method

	GET

##Request Parameters
    
    None

##Query Parameters

	*workGroupId* - integer value indicating the workgroup (required)
	*startDate* - date value indicating the start date from which to retrieve posts (required)
	*endDate* - date value indicating the end date from which to retrieve posts (required)
	*network* - string value indicating social network for post:
		*all* (default)
		*facebook*
		*twitter*
		*linkedin*
		*gplus*
		*youtube*
		*instagram*
	*socialProperty* - string values (in a comma-delimited list) indicating the social properties from which to retrieve the post (defaults to all social properties included in workspace)
	*socialAsset* - string value indicating the Social Account Set ID from a workspace (defaults to all social accounts included in workspace)
	*metrics* - string values (in a comma-delimited list) included in the response:
		*facebook*
			*likes*
			*comments*
			*shares*
			*reach*
			*organic_reach*
			*viral_reach*
			*paid_reach*
			*fan_reach*
			*non_fan_reach*
			*fan_paid_reach*
			*engagement*
			*clicks*
			*engagement_rate*
		*twitter*
			*retweets*
			*replies*
			*favorites*
			*link_clicks*
			*engagement*
			*engagement_rate*
		*linkedin*
			*likes*
			*comments*
			*link_clicks*
			*engagement*
		*gplus*
			*plusone*
			*reshares*
			*comments*
			*link_clicks*
			*engagement*
		*youtube*
			*views*
			*likes*
			*dislikes*
			*comments*
			*link_clicks*
			*engagement*
		*instagram*
			*likes*
			*comments*
	*labels* - string value (in a comma-delimited list) indicating labels to use in filter
	*type* - string value indicating media type to use in filter
	*orderBy* - string value indicating parameter used to sort results (defaults to date)
	*order* - string value indicating display direction for retrieved content (defaults to DESC):
		*DESC* - descending order (default)
		*ASC* - ascending order
	*page* - integer value indicating which page to display from retreived data (defaults to 1)
	*perpage* - integer value indicating how many results to include in a page (defaults to 10)
	*filter* - string value indicating publish status of post (defaults to unpublished)

##Request Parameter Example
	
	GET /v1/importedposts

##Sample Request

The call below retrieves all imported posts from a specified workspace:
```
GET /v1/importedposts?workspace=1
```

The call below retrieves all imported Facebook posts from a specified workspace:
```
GET /v1/importedposts?workspace=1&network=facebook
```

The call below retrieves all imported Facebook posts from a specified workspace with specified metrics:
```
GET /v1/importedposts?workspace=1&network=facebook&metrics=likes,comments
```

The call below retrieves all imported Facebook posts from a specified workspace with specified metrics:
```
GET /v1/importedposts?workspace=1&network=facebook&metrics=likes,comments&orderBy=comments
```

##Sample Response

Each imported post includes the following properties:

	*id* - string value with unique ID of imported post
	*created* - string value containing the timestamp of when post first existed on the social network (NOT when it first existed in Social Studio)
	*deleted* - boolean value indicated a deleted imported post
	*external_post_id* - string value containing the external post ID from the imported post created in the social account (such as a Facebook post ID)
	*media_type* - integer value indicating the media type for the imported post:
		*1* - MEDIA_TYPE_ALBUM
		*2* - MEDIA_TYPE_LINK
		*3* - MEDIA_TYPE_PHOTO
		*4* - MEDIA_TYPE_STATUS
		*5* - MEDIA_TYPE_VIDEO
	*message* - string value indicating content of imported post
	*metadata* - array of information about the imported post object
		*id* - string value indicating ID of metadata
		*created* - string value containing timestamp of when metadata first existed
		*deleted* - boolean value indicated deleted metadata
		*imported_id* - ID for imported post associated with metadata
		*key* string value indicating metadata type
		*provider* - provider object indicating source of metadata information
		*updated* - string value indicating timestamp of last update for metadata
		*value* - string value indicating metadata value
	*network_id* - integer value indicating network associated with social account:
		*1* - NETWORK_FACEBOOK
		*2* - NETWORK_TWIITER
		*3* - NETWORK_PLUS
		*4* - NETWORK_LINKEDIN
	*networkasset_id* - string value indicating imported post type
	*type* - integer value indicating imported post type:
		*1* - TYPE_FACEBOOK_POST
        *2* - TYPE_FACEBOOK_COMMENT
        *3* - TYPE_FACEBOOK_COMMENT_REPLY
        *4* - TYPE_FACEBOOK_LIKE
        *100* - TYPE_TWITTER_TWEET
        *101* - TYPE_TWITTER_RETWEET
        *102* - TYPE_TWITTER_REPLY
        *103* - TYPE_TWITTER_FAVORITE
    *updated* - string value indicating timestamp of last update for imported post

A successful call returns posts from all networks in last seven days in descending order:
```
{
    "status": true,
    "response": [
        {
            "id": "35db3b27-edd5-4d35-8ef7-574b0f483524",
            "socialAsset": "200012913364042",
            "socialProperty": 8307,
            "slug": "/Buddy-The-Dog/200012913364042",
            "assets": {
                "id": 46,
                "created": "2013-08-12T10:48:28-0400",
                "metadata": "{\"link_type\":\"link\",\"title\":\"CRM and Cloud Computing To Grow Your Business - Salesforce.com\",\"caption\":\"http://Salesforce.com\",\"description\":\"You can change stuff here\",\"images\":[\"http://www.sfdcstatic.com/common/assets/img/logo-company.png\"],\"image_index\":0,\"thumbnail\":true,\"share_link\":false,\"url\":\"http://Salesforce.com\",\"video_src\":null,\"type\":\"link\"}",
                "post_id": "35db3b27-edd5-4d35-8ef7-574b0f483524",
                "type": 3,
                "updated": "2013-08-12T10:48:28-0400",
                "url": "http://Salesforce.com"
            },
            "date": "2013-08-13 09:45:03",
            "message": "Salesforce.com is cool!",
            "network": "facebook",
            "targeting": [ ],
            "labels" : [ ],
            "type": "status",
            "socialAssetName": "Buddy - The Dog",
            "blogPostId": 1234
        },
        {
            "id": "b93ab12e-37cd-4344-bffa-3a59f5053580",
            "socialAsset": "200012913364042",
            "socialProperty": 8307,
            "slug": "/Buddy-The-Dog/200012913364042",
            "assets": [ ],
            "date": "2013-08-12 15:29:40",
            "message": "yahoo.com",
            "network": "facebook",
            "targeting": [ ],
            "labels" : [ ],
            "type": "status",
            "socialAssetName": "Buddy - The Dog",
            "blogPostId": 1234
        },
        {
            "id": "9bc25322-49ca-4b9c-ae81-20ff1b593edf",
            "socialAsset": "200012913364042",
            "socialProperty": 8307,
            "slug": "/Buddy-The-Dog/200012913364042",
            "assets": {
                "id": 47,
                "created": "2013-08-12T10:48:29-0400",
                "metadata": "{\"link_type\":\"link\",\"title\":\"CRM and Cloud Computing To Grow Your Business - Salesforce.com\",\"caption\":\"http://Salesforce.com\",\"description\":\"You can change stuff here\",\"images\":[\"http://www.sfdcstatic.com/common/assets/img/logo-company.png\"],\"image_index\":0,\"thumbnail\":true,\"share_link\":false,\"url\":\"http://Salesforce.com\",\"video_src\":null,\"type\":\"link\"}",
                "post_id": "9bc25322-49ca-4b9c-ae81-20ff1b593edf",
                "type": 3,
                "updated": "2013-08-12T10:48:29-0400",
                "url": "http://Salesforce.com"
            },
            "date": "2013-08-12 09:45:03",
            "message": "Salesforce.com is cool!",
            "network": "facebook",
            "targeting": [ ],
            "labels" : [ ],
            "type": "status",
            "socialAssetName": "Buddy - The Dog",
            "blogPostId": 1234
        }
        ...
    ],
    "meta": {
       "total": 6,
       "perpage": 10,
       "current": 1,
       "prev": "",
       "next": ""
    }
}
```

A successful call returns posts from Facebook in last seven days in descending order:
```
{
    "status": true,
    "response": [
        {
            "id": "35db3b27-edd5-4d35-8ef7-574b0f483524",
            "socialAsset": "200012913364042",
            "socialProperty": 8307,
            "slug": "/Buddy-The-Dog/200012913364042",
            "assets": {
                "id": 46,
                "created": "2013-08-12T10:48:28-0400",
                "metadata": "{\"link_type\":\"link\",\"title\":\"CRM and Cloud Computing To Grow Your Business - Salesforce.com\",\"caption\":\"http://Salesforce.com\",\"description\":\"You can change stuff here\",\"images\":[\"http://www.sfdcstatic.com/common/assets/img/logo-company.png\"],\"image_index\":0,\"thumbnail\":true,\"share_link\":false,\"url\":\"http://Salesforce.com\",\"video_src\":null,\"type\":\"link\"}",
                "post_id": "35db3b27-edd5-4d35-8ef7-574b0f483524",
                "type": 3,
                "updated": "2013-08-12T10:48:28-0400",
                "url": "http://Salesforce.com"
            },
            "date": "2013-08-13 09:45:03",
            "message": "Salesforce.com is cool!",
            "network": "facebook",
            "targeting": [ ],
            "labels" : [ ],
            "type": "status",
            "socialAssetName": "Buddy - The Dog",
            "blogPostId": 1234
        },
        {
            "id": "9bc25322-49ca-4b9c-ae81-20ff1b593edf",
            "socialAsset": "200012913364042",
            "socialProperty": 8307,
            "slug": "/Buddy-The-Dog/200012913364042",
            "assets": {
                "id": 47,
                "created": "2013-08-12 10:48:29",
                "metadata": "{\"link_type\":\"link\",\"title\":\"CRM and Cloud Computing To Grow Your Business - Salesforce.com\",\"caption\":\"http://Salesforce.com\",\"description\":\"You can change stuff here\",\"images\":[\"http://www.sfdcstatic.com/common/assets/img/logo-company.png\"],\"image_index\":0,\"thumbnail\":true,\"share_link\":false,\"url\":\"http://Salesforce.com\",\"video_src\":null,\"type\":\"link\"}",
                "post_id": "9bc25322-49ca-4b9c-ae81-20ff1b593edf",
                "type": 3,
                "updated": "2013-08-12T10:48:29-0400",
                "url": "http://Salesforce.com"
            },
            "date": "2013-08-12 09:45:03",
            "message": "Salesforce.com is cool!",
            "network": "facebook",
            "targeting": [ ],
            "labels" : [ ],
            "type": "status",
            "socialAssetName": "Buddy - The Dog",
            "blogPostId": 1234
        }
        ...
    ],
    "meta": {
       "total": 16,
       "perpage": 10,
       "current": 1,
       "prev": "",
       "next": ""
    }
}
```

A successful call returns posts from Facebook in last seven days in descending order with metrics:
```
{
    "status": true,
    "response": [
        {
            "id": "35db3b27-edd5-4d35-8ef7-574b0f483524",
            "socialAsset": "200012913364042",
            "socialProperty": 8307,
            "slug": "/Buddy-The-Dog/200012913364042",
            "assets": {
                "id": 46,
                "created": "2013-08-12T10:48:28-0400",
                "metadata": "{\"link_type\":\"link\",\"title\":\"CRM and Cloud Computing To Grow Your Business - Salesforce.com\",\"caption\":\"http://Salesforce.com\",\"description\":\"You can change stuff here\",\"images\":[\"http://www.sfdcstatic.com/common/assets/img/logo-company.png\"],\"image_index\":0,\"thumbnail\":true,\"share_link\":false,\"url\":\"http://Salesforce.com\",\"video_src\":null,\"type\":\"link\"}",
                "post_id": "35db3b27-edd5-4d35-8ef7-574b0f483524",
                "type": 3,
                "updated": "2013-08-12T10:48:28-0400",
                "url": "http://Salesforce.com"
            },
            "date": "2013-08-13 09:45:03",
            "message": "Salesforce.com is cool!",
            "network": "facebook",
            "targeting": [ ],
            "labels" : [ ],
            "type": "status",
            "socialAssetName": "Buddy - The Dog",
            "blogPostId": 1234,
            "metrics": {
                "likes": 300,
                "comments": 400
            }
        },
        {
            "id": "9bc25322-49ca-4b9c-ae81-20ff1b593edf",
            "socialAsset": "200012913364042",
            "socialProperty": 8307,
            "slug": "/Buddy-The-Dog/200012913364042",
            "assets": {
                "id": 47,
                "created": "2013-08-12T10:48:29-0400",
                "metadata": "{\"link_type\":\"link\",\"title\":\"CRM and Cloud Computing To Grow Your Business - Salesforce.com\",\"caption\":\"http://Salesforce.com\",\"description\":\"You can change stuff here\",\"images\":[\"http://www.sfdcstatic.com/common/assets/img/logo-company.png\"],\"image_index\":0,\"thumbnail\":true,\"share_link\":false,\"url\":\"http://Salesforce.com\",\"video_src\":null,\"type\":\"link\"}",
                "post_id": "9bc25322-49ca-4b9c-ae81-20ff1b593edf",
                "type": 3,
                "updated": "2013-08-12T10:48:29-0400",
                "url": "http://Salesforce.com"
            },
            "date": "2013-08-12 09:45:03",
            "message": "Salesforce.com is cool!",
            "network": "facebook",
            "targeting": [ ],
            "labels" : [ ],
            "type": "status",
            "socialAssetName": "Buddy - The Dog",
            "blogPostId": 1234,
            "metrics": {
                "likes": 100,
                "comments": 800
            }
        }
        ...
    ],
    "meta": {
       "total": 16,
       "perpage": 10,
       "current": 1,
       "prev": "",
       "next": ""
    }
}
```

A successful call returns posts from Facebook in last seven days sorted by comments in descending order with metrics:
```
{
    "status": true,
    "response": [
        {
            "id": "35db3b27-edd5-4d35-8ef7-574b0f483524",
            "socialAsset": "200012913364042",
            "socialProperty": 8307,
            "slug": "/Buddy-The-Dog/200012913364042",
            "assets": {
                "id": 46,
                "created": "2013-08-12T10:48:28-0400",
                "metadata": "{\"link_type\":\"link\",\"title\":\"CRM and Cloud Computing To Grow Your Business - Salesforce.com\",\"caption\":\"http://Salesforce.com\",\"description\":\"You can change stuff here\",\"images\":[\"http://www.sfdcstatic.com/common/assets/img/logo-company.png\"],\"image_index\":0,\"thumbnail\":true,\"share_link\":false,\"url\":\"http://Salesforce.com\",\"video_src\":null,\"type\":\"link\"}",
                "post_id": "35db3b27-edd5-4d35-8ef7-574b0f483524",
                "type": 3,
                "updated": "2013-08-12T10:48:28-0400",
                "url": "http://Salesforce.com"
            },
            "date": "2013-08-13 09:45:03",
            "message": "Salesforce.com is cool!",
            "network": "facebook",
            "targeting": [ ],
            "labels" : [ ],
            "type": "status",
            "socialAssetName": "Buddy - The Dog",
            "blogPostId": 1234,
            "metrics": {
                "likes": 300,
                "comments": 800
            },
            "blogPostId": 1234
        },
        {
            "id": "9bc25322-49ca-4b9c-ae81-20ff1b593edf",
            "socialAsset": "200012913364042",
            "socialProperty": 8307,
            "slug": "/Buddy-The-Dog/200012913364042",
            "assets": {
                "id": 47,
                "created": "2013-08-12T10:48:29-0400",
                "metadata": "{\"link_type\":\"link\",\"title\":\"CRM and Cloud Computing To Grow Your Business - Salesforce.com\",\"caption\":\"http://Salesforce.com\",\"description\":\"You can change stuff here\",\"images\":[\"http://www.sfdcstatic.com/common/assets/img/logo-company.png\"],\"image_index\":0,\"thumbnail\":true,\"share_link\":false,\"url\":\"http://Salesforce.com\",\"video_src\":null,\"type\":\"link\"}",
                "post_id": "9bc25322-49ca-4b9c-ae81-20ff1b593edf",
                "type": 3,
                "updated": "2013-08-12T10:48:29-0400",
                "url": "http://Salesforce.com"
            },
            "date": "2013-08-12 09:45:03",
            "message": "Salesforce.com is cool!",
            "network": "facebook",
            "targeting": [ ],
            "labels" : [ ],
            "type": "status",
            "socialAssetName": "Buddy - The Dog",
            "blogPostId": 1234,
            "metrics": {
                "likes": 100,
                "comments": 600
            }
        }
        ...
    ],
    "meta": {
       "total": 16,
       "perpage": 10,
       "current": 1,
       "prev": "",
       "next": ""
    }
}
```

    *id* - string value indicating ID of imported content
    *socialAsset* - string value indicating ID of social asset
    *socialProperty* - string value indicating ID of social property
    *slug* - string value of slug for imported content
    *assets* - array of information on assets within imported content
        *id* - string value including ID for imported content
        *created* - timestamp value indicating asset creation data
        *metadata* - string value including metadata associated with imported content
        *post_id* - string value including ID for post associated with content
        *type* - integer value indicating type of asset
        *updated* - timestamp value indicating asset updating data
        *url* - string value including URL for asset
    *date* - timestamp value indicating date for content creation
    *message* - string value including message of content
    *network* - string value including social network used for content
    *targeting* - string value indicating targeting for content
    *labels* - string value indicating labels for content
    *type* - string value indicating type of content within social network (such as update)
    *socialAssetName* - string value including name of content from social network
    *blogPostId* - string value indicating ID of associated blog post
    *metrics* - array of information about social content analytics
        *likes* - integer value of social network likes
        *comments* - integer value of social network comments