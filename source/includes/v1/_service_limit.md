# Service Limit #

The `Service Limit` API allows you to retrieve the service limits for product's APIs.


## Retrieve service quota limit ##

This API helps you to retrieve the service limit.


### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">GET</i>
		<h6>/customer/service-quota</h6>
	</div>
</div>

### Response ###

### ServiceLimits ###

| Attribute | Type  | Description           |
|-----------|-------|-----------------------|
| `data`    | array | List of ServiceLimit. |

### ServiceLimit ###

| Attribute           | Type    | Description                                                |
|---------------------|---------|------------------------------------------------------------|
| `id`                | integer | Id of the service limit.                                   |
| `expired_at`        | integer | Expired time for this service limit .                      |
| `service_type`      | enum    | Indicates for which service, this limit is applicable for. |
| `limitation_type`   | enum    | Indicates weather customer have limit or not.              |
| `interval_type`     | enum    | Indicates the interval type for this limit.                |
| `interval_duration` | integer | Indicates the number of interval this limit is applicable. |
| `available_limit`   | integer | Indicates the remaining quota for this service limit.      |

### Example ###

{
  "id": 1,
  "user_id": 7950,
  "oauth_client_id": null,
  "expired_at": "2023-05-18T14:54:54.000000Z",
  "service_type": "inventory-product-fetch",
  "limitation_type": "have-limit",
  "interval_type": "year",
  "interval_duration": 1,
  "last_avail_time": "2022-05-18 14:54:54",
  "available_limit": 262
}

According to the above service limit, there is a limitation on the amount of products a customer can fetch from inventory.
Customers can still fetch 262 products.


> Example of retrieving service limit

```shell
curl -X GET https://moveon-api-server.sbox.ali2bd.net/api/v1/customer/service-quota\
	-H "Authorization: Bearer %token%" \
	-H "Content-Type: application/json"
```

> JSON response example:

```json
{
  "data": [
    {
      "id": 1,
      "user_id": 7950,
      "oauth_client_id": null,
      "expired_at": "2023-05-18T14:54:54.000000Z",
      "service_type": "inventory-product-fetch",
      "limitation_type": "have-limit",
      "interval_type": "year",
      "interval_duration": 1,
      "last_avail_time": "2022-05-18 14:54:54",
      "available_limit": 262
    }
  ]
}
```
