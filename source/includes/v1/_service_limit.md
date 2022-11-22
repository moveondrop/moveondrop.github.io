# ServiceLimit #

The ServiceLimit API allows you to retrieve the service limits for product's APIs.


### Retrieve service limit ###

This API helps you to retrieve the service limit.


### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">GET</i>
		<h6>/customer/service-quota</h6>
	</div>
</div>


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
