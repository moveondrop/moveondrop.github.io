# Location #

The Location API allows you to retrieve locations.


## Retrieve all districts ##

This API helps you to retrieve all the districts.


### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">GET</i>
		<h6>/location</h6>
	</div>
</div>


> Example of retrieving all districts:

```shell
curl -X GET BASE_URL/api/v1/location \
	-H "Authorization: Bearer %token%" \
	-H "Content-Type: application/json"
```

> JSON response example:

```json
{
  "data": [
    {
      "id": 1,
      "parent_id": null,
      "slug": "bagerhat",
      "name": "Bagerhat",
      "postal_code": null,
      "type": "district"
    },
    {
      "id": 2,
      "parent_id": null,
      "slug": "bandarban",
      "name": "Bandarban",
      "postal_code": null,
      "type": "district"
    },
    {
      "id": 3,
      "parent_id": null,
      "slug": "barguna",
      "name": "Barguna",
      "postal_code": null,
      "type": "district"
    }
  ]
}
```


## Retrieve areas for a district ##

This API helps you to retrieve areas under a district.

### Request ###

### Available query parameters ###

| Attribute       | Type    | Description                                                |
|-----------------|---------|------------------------------------------------------------|
| `parent`        | integer | Id of the district                                         |


### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">GET</i>
		<h6>/location?parent=:parentId</h6>
	</div>
</div>


> Example of retrieving areas under a district:

```shell
curl -X GET BASE_URL/api/v1/location?parent=13 \
	-H "Authorization: Bearer %token%" \
	-H "Content-Type: application/json"
```

> JSON response example:

```json
{
  "data": [
    {
      "id": 198,
      "parent_id": 13,
      "slug": "adabar",
      "name": "Adabar",
      "postal_code": 1207,
      "type": "area"
    },
    {
      "id": 199,
      "parent_id": 13,
      "slug": "agargoan",
      "name": "Agargoan",
      "postal_code": 1216,
      "type": "area"
    },
    {
      "id": 200,
      "parent_id": 13,
      "slug": "ahamedbag",
      "name": "Ahamedbag",
      "postal_code": 1214,
      "type": "area"
    }
  ]
}
```
