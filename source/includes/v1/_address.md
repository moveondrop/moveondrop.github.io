# Address #

The address API allows managing addresses.

## Get all addresses ##

This API helps you to retrieve all addresses.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">GET</i>
		<h6>/customer/profile/address</h6>
	</div>
</div>


> Example of retrieving all addresses:

```shell
curl -X POST https://moveon-api-server.sbox.ali2bd.net/api/v1/customer/profile/address \
	-H "Authorization: Bearer %token%" \
	-H "Content-Type: application/json"
```


> JSON response example:

```json
{
  "data": [
    {
      "id": 1611,
      "name": "Test address",
      "phone": "0000000000000",
      "country": "Bangladesh",
      "district": {
        "id": 13,
        "parent_id": null,
        "slug": "dhaka",
        "name": "Dhaka",
        "postal_code": null,
        "type": "district"
      },
      "area": {
        "id": 199,
        "parent_id": 13,
        "slug": "agargoan",
        "name": "Agargoan",
        "postal_code": 1216,
        "type": "area"
      },
      "address": "Test address",
      "postal_code": 1213,
      "is_default_shipping": 1,
      "is_default_billing": 1
    }
  ]
}
```

## Get default addresses ##

This API helps you to retrieve default addresses.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">GET</i>
		<h6>/customer/profile/address/default</h6>
	</div>
</div>


> Example of retrieving default addresses:

```shell
curl -X POST https://moveon-api-server.sbox.ali2bd.net/api/v1/customer/profile/address/default \
	-H "Authorization: Bearer %token%" \
	-H "Content-Type: application/json"
```


> JSON response example:

```json
{
  "data": {
    "billing": {
      "id": 1611,
      "name": "Test address update",
      "phone": "0000000000000",
      "country": "Bangladesh",
      "district": {
        "id": 13,
        "parent_id": null,
        "slug": "dhaka",
        "name": "Dhaka",
        "postal_code": null,
        "type": "district"
      },
      "area": {
        "id": 199,
        "parent_id": 13,
        "slug": "agargoan",
        "name": "Agargoan",
        "postal_code": 1216,
        "type": "area"
      },
      "address": "Test address",
      "postal_code": 1213,
      "is_default_shipping": 1,
      "is_default_billing": 1
    },
    "shipping": {
      "id": 1611,
      "name": "Test address update",
      "phone": "0000000000000",
      "country": "Bangladesh",
      "district": {
        "id": 13,
        "parent_id": null,
        "slug": "dhaka",
        "name": "Dhaka",
        "postal_code": null,
        "type": "district"
      },
      "area": {
        "id": 199,
        "parent_id": 13,
        "slug": "agargoan",
        "name": "Agargoan",
        "postal_code": 1216,
        "type": "area"
      },
      "address": "Test address",
      "postal_code": 1213,
      "is_default_shipping": 1,
      "is_default_billing": 1
    }
  }
}
```

## Store an address ##

This API helps you to store a new address.

## Create/Update address properties ##

| Attribute             | Type    | Description                                       |
|-----------------------|---------|---------------------------------------------------|
| `name`                | string  | Person name                                       |
| `phone`               | string  | Person phone number                               |
| `country`             | string  | Currently supported countries is "Bangladesh"     |
| `district`            | integer | District id (It can be found from Location API)   |
| `area`                | integer | Area id (It can be found from Location API)       |
| `address`             | string  | Actual address (House, Landmark, Road)            |
| `postal_code`         | integer | The postal code this address belongs to           |
| `is_default_shipping` | boolean | Weather this address is default shipping  address |
| `is_default_billing`  | boolean | Weather this address is default billing  address  |


### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">POST</i>
		<h6>/customer/profile/address</h6>
	</div>
</div>


> Example of store an address:

```shell
curl -X POST https://moveon-api-server.sbox.ali2bd.net/api/v1/customer/profile/address \
	-H "Authorization: Bearer %token%" \
	-H "Content-Type: application/json" \
	-d '{
    "name": "Test address",
    "phone": "0000000000000",
    "country": "Bangladesh",
    "district": 13,
    "area": 199,
    "address" : "Test address",
    "postal_code": 1213,
    "is_default_shipping": true,
    "is_default_billing": true
}'
```


> JSON response example:

```json
{
  "message": "Address created successfully",
  "address": {
    "id": 1612,
    "name": "Test address",
    "phone": "0000000000000",
    "country": "Bangladesh",
    "district": {
      "id": 13,
      "parent_id": null,
      "slug": "dhaka",
      "name": "Dhaka",
      "postal_code": null,
      "type": "district"
    },
    "area": {
      "id": 199,
      "parent_id": 13,
      "slug": "agargoan",
      "name": "Agargoan",
      "postal_code": 1216,
      "type": "area"
    },
    "address": "Test address",
    "postal_code": 1213,
    "is_default_shipping": 1,
    "is_default_billing": 1
  }
}
```


## Update an address ##

This API helps you to update an existing address.


### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">PUT</i>
		<h6>/customer/profile/address/:addressId</h6>
	</div>
</div>


> Example of updating an existing address:

```shell
curl -X PUT https://moveon-api-server.sbox.ali2bd.net/api/v1/customer/profile/address/1610\
	-H "Authorization: Bearer %token%" \
	-H "Content-Type: application/json" \
	-d '{
	"name": "Test address update",
	"phone": "0000000000000",
	"country": "Bangladesh",
	"district": 13,
	"area": 199,
	"address" : "Test address",
	"postal_code": 1213,
	"is_default_shipping": true,
	"is_default_billing": true
}'
```



## Delete an address ##

This API helps you to delete an existing address.


### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">DELETE</i>
		<h6>/customer/profile/address/:addressId</h6>
	</div>
</div>


> Example of deleting an existing address:

```shell
curl -X DELETE https://moveon-api-server.sbox.ali2bd.net/api/v1/customer/profile/address/1610\
	-H "Authorization: Bearer %token%" \
	-H "Content-Type: application/json"
```

> JSON response example:

```json
{
  "message": "Address deleted successfully"
}
```
