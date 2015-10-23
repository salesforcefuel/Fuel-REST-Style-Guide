This method retrieves performance activity associated with a specific clip within a workspace.

##Resource

	/v1/clips/

##HTTP Method

	GET

##Request Parameters

	*id* - ID for the specified clip
	*workspace* - string value indicating activities for clip within a workspace:
		*avg_engagement* - integer indicating average engagement performance (default)
		*engagement* - integer indicating total engagement performance
	*post* - string value indicating activities for clip within a post:
		*created* - date value indicating time of creation (default)
		*engagement* - integer indicating total engagement performance
		*engagement_rate* - integer indicating rate of engagement
	*network* - string value indicating activities for clip within a social network:
		*avg_engagement* - integer indicating average engagement performance (default)
		*engagement* - integer indicating total engagement performance
		*engagement_rate* - integer indicating rate of engagement
	*usage* - string value indicating usage of clip
	*direction* - string value indicating display direction for retrieved content:
		*desc* - descending order (default)
		*asc* - ascending order
	*page* - integer value indicating which page to display from retreived data (defaults to 1)
	*perpage* - integer value indicating how many results to include in a page (defaults to 10)

##Request Parameter Example

	GET /clips/{id}/performance?action=workspace&sort=engagement

##Sample Request

The sample call below request activities for a clip from a workspace:
```
	GET /clips/35543aba-18b2-4995-bb76-ea1132fe544a/performance?action=workspace&sort=engagement
```

The sample call below request activities for a clip from a post:
```
	GET /clips/35543aba-18b2-4995-bb76-ea1132fe544a/performance?action=post&sort=engagement&page=1&perpage=10&direction=desc
```

The sample call below request activities for a clip from a network:
```
	GET /clips/35543aba-18b2-4995-bb76-ea1132fe544a/performance?action=network&sort=engagement
```

The sample call below request activities for a clip from overall usage:
```
	GET /clips/35543aba-18b2-4995-bb76-ea1132fe544a/performance?action=usage
```

##Sample Response

A successful workspace call returns the following response:
```
# HTTP 200 Success
{
    "status": true,
    "response":[
       {
           "id": "aa556431-71ce-494b-9e82-9d5e539802e5",
           "name": "Brrrrr",
           "logo": "https://d2ee3wvl22m8i7.cloudfront.net/1398882826058_guy_bourdin.jpg",
           "post_count": "1",
           "value": "25"
       },
       {
           "id": "ab8b7a66-6949-4d2e-aaf7-fe923421cd23",
           "name": "13thMay2014",
           "logo": null,
           "post_count": "4",
           "value": "0"
       },
       {
           "id": "1d4a953e-b44a-44dd-8602-56b5310aacbc",
           "name": "ANA",
           "logo": "https://d2ee3wvl22m8i7.cloudfront.net/1399663189853_456730_10150833224116583_591494996_o.jpg",
           "post_count": "14",
           "value": "0"
       },
       {
           "id": "e210b219-3eea-42e8-af8f-6725af02c668",
           "name": "5thMay",
           "logo": null,
           "post_count": "18",
           "value": "0"
       }
    ]
    "meta":[]
}
```

  *status* - string value indicating success of call
  *response* - array of values containing information on clip performance
    *id* - string value indicating ID for content
    *name* - string value indicating name for content
    *logo* - string value containing URL of image file used for logo
    *post_count* - integer value indicating post count
    *value* - integer value indicating value of content


A successful post call returns the following response:
```
# HTTP 200 Success
{
    "status": true,
    "response":[
       {
           "id": "47f23f23-3cd8-4202-861f-6c0c4f2b2a95",
           "network": "Facebook",
           "name": "2011vg",
           "slug": "/2011vg/631660596857171",
           "logo": "https://fbcdn-profile-a.akamaihd.net/static-ak/rsrc.php/v2/yg/r/LjGkeBM0ISt.png",
           "engagement": "25",
           "engagement_rate": "0.5",
           "targeting": "global",
           "publish_date": "2014-05-19 17:01:19"
       },
       {
           "id": "f5fb2046-f6fd-4f5f-9caf-18205864b1dc",
           "network": "Twitter",
           "name": "SFDCBMIT41",
           "slug": "@SFDCBMIT41",
           "logo": "http://abs.twimg.com/sticky/default_profile_images/default_profile_3_normal.png",
           "engagement": "0",
           "engagement_rate": "0",
           "targeting": "global",
           "publish_date": "2014-05-19 18:29:18"
       },
       {
           "id": "97d5058a-e5ce-48ac-8e82-59bd3ba667be",
           "network": "Twitter",
           "name": "SFDCBMIT21",
           "slug": "@SFDCBMIT21",
           "logo": "http://pbs.twimg.com/profile_images/378800000867632840/75LTUnsB_normal.png",
           "engagement": "0",
           "engagement_rate": "0",
           "targeting": "global",
           "publish_date": "2014-05-19 18:29:16"
       },
       ...
    ]
    "meta":[
       "total": 37,
       "page": 1,
       "perpage": 10,
       "current": "/v1/clips/hiren-test-post-for-checking-metrics/performance?action=post&sort=engagement&page=1",
       "prev": "",
       "next": "/v1/clips/hiren-test-post-for-checking-metrics/performance?action=post&sort=engagement&page=2"
    ]
}
```
  *status* - string value indicating success of call
  *response* - array of information on content
   *id* - integer value indicating ID for content
    *network* - string value indicating social network for content
    *name* - string value with name for content
    *slug* - string value indicating slug content for social network
    *logo* - string value contauning 
    *engagement* - integer value indicating number of engagements with content
    *engagement_rate* - integer value indicating average engagement with content
    *targeting* - string value indicating targeting for content
    *publish_date* - timestamp value indicating date of publishing for content


A successful network call returns the following response:
```
# HTTP 200 Success
{
    "status": true,
    "response":[
       {
           "network": "Facebook",
           "post_count": "33",
           "value": "25"
       },
       {
           "network": "Twitter",
           "post_count": "4",
           "value": "0"
       }
    ]
    "meta":[]
}
```

  *status* - string value indicating success of call
  *response* - array of information on content
    *network* - string value indicating social network for content
      *post_count* - integer value indicating post count
    *value* - integer value indicating value of content

A successful usage call returns the following response:
```
# HTTP 200 Success
{
    "status": true,
    "response":{
        "workspace": "5",
        "published": "37",
        "scheduled": "1",
        "draft": "0"
    },
    "meta":[]
}
```

  *status* - string value indicating success of call
  *response* - array of information on content
    *workspace* - integer value identifying workspace
    *published* - integer value identifying number of published posts in workspace
    *scheduled* - integer value identifying number of scheduled posts in workspace
    *draft* - integer value identifying number of draft posts in workspace