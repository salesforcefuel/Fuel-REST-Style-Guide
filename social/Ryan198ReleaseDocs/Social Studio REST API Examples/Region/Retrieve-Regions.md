This method returns all regions associated with an account.

##Resources

	v3/regions

##HTTP Method

	GET

##Request Parameters

	*limit* - integer value indicating number of results to return (defaults to 1000)
	*offset* - integer value indicating result to start with (defaults to 0)

##Request Parameter Example

	GET	v3/regions

##Sample Call
```
	GET	v3/regions
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
    },
    {
      "id": "78",
      "title": "French Southern Territories",
      "regionTLD": ".tf",
      "isoCountryCode": "TF"
    },
    {
      "id": "158",
      "title": "New Caledonia",
      "regionTLD": ".nc",
      "isoCountryCode": "NC"
    },
    ...
  ],
  "meta": {
    "totalCount": 249
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
