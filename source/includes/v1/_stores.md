# Store #

The Store API allows you to retrieve store information with rates.


## Retrieve stores ##

This API helps you to retrieve store information.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">POST</i>
		<h6>/customer/exclusive/store-rates</h6>
	</div>
</div>


## Retrieve store properties ##

| Attribute | Type      | Description   |
|-----------|-----------|---------------|
| `data`    | array     | List of Store |

### Store - StoreItem ###

| Attribute          | Type    | Description                                                       |
|--------------------|---------|-------------------------------------------------------------------|
| `id`               | integer | Id of the store.                                                  |
| `name`             | string  | Name of the store.                                                |
| `vendor_name`      | string  | Name of the vendor.                                               |
| `storeId`          | integer | Actual storeId (During the order placement, this value is needed) |
| `url`              | string  | URL of this store                                                 |
| `totalFx`          | decimal | Total exchange rate for this store                                |                         |                                      |
| `min_order_amount` | decimal | Minimum order total limit for this store                          |                                      |

> Example of retrieve stores:

```shell
curl -X GET BASE_URL/api/v1/customer/exclusive/store-rates \
	-H "Authorization: Bearer %token%" \
	-H "Content-Type: application/json"
```

> JSON response example:

```json
{
  "data": [
    {
      "id": 1,
      "name": "1688",
      "vendor_name": "1688",
      "storeId": 10,
      "url": "www.1688.com",
      "totalFx": 18.64,
      "min_order_amount": "2500.00"
    },
    {
      "id": 2,
      "name": "Taobao",
      "vendor_name": "Taobao",
      "storeId": 4,
      "url": "https://taobao.com",
      "totalFx": 16.4862,
      "min_order_amount": "500.00"
    },
    {
      "id": 3,
      "name": "AliExpress",
      "vendor_name": "AliExpress",
      "storeId": 1,
      "url": "https://www.aliexpress.com",
      "totalFx": 120.96000000000001,
      "min_order_amount": "2500.00"
    },
    {
      "id": 4,
      "name": "Alibaba",
      "vendor_name": "alibaba",
      "storeId": 11,
      "url": "https://alibaba.com",
      "totalFx": 94.688,
      "min_order_amount": "3000.00"
    },
    {
      "id": 5,
      "name": "AmazonUSA",
      "vendor_name": "amazon",
      "storeId": 12,
      "url": "https://amazon.com",
      "totalFx": 94.1424,
      "min_order_amount": null
    },
    {
      "id": 6,
      "name": "Pinduoduo",
      "vendor_name": "Pingduoduo",
      "storeId": 14,
      "url": "https://pingduoduo.com",
      "totalFx": 16.4862,
      "min_order_amount": null
    },
    {
      "id": 7,
      "name": "Ebay",
      "vendor_name": "ebay USA",
      "storeId": 16,
      "url": "https://ebay.com",
      "totalFx": 93.7228,
      "min_order_amount": null
    }
  ]
}
```
