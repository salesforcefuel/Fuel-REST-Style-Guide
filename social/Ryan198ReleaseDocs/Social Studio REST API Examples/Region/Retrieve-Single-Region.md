This method returns a specific region associated with an account.

##Resources

	v3/regions

##HTTP Method

	GET

##Request Parameters

	*regionId* - integer value indicating internal ID for region

##Request Parameter Example

	GET	v3/regions/{regionId}

##Sample Call
```
	GET	v3/regions/46
```

##Sample Response
```
{
  "data": [
    {
      "id": "46",
      "title": "China",
      "regionTLD": ".cn",
      "isoCountryCode": "CN"
    }
  ],
  "meta": {
    "totalCount": 1
  }
}
```

	*data* - object containing references to regions within account:
		*id* - integer value indicating internal ID for region
		*link* - string value indicating direct API link to region
		*updated* - timestamp value including date region added to account
		*title* - string value including English name for region
		*regionTLD* - string value including top-level domain for region
		*isoCountryCode* - string value including ISO country code