# Orders #

The orders API allows you to create, view of orders.


## Create an order ##

This API helps you to create a new order.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">POST</i>
		<h6>/customer/buy-ship/orders-by-products</h6>
	</div>
</div>


## Create order properties ##

| Attribute              | Type      | Description                                                                        |
|------------------------|-----------|------------------------------------------------------------------------------------|
| `products`             | array     | List of products. See [Order - Meta data properties](#order-meta-data-properties)  |
| `address`              | object    | Line items data. See [Order - Line items properties](#order-line-items-properties) |

### Order - Product ###

| Attribute   | Type   | Description                                                 |
|-------------|--------|-------------------------------------------------------------|
| `title`     | string | Title of the product.                                       |
| `vid`       | string | Vid of the product.                                         |
| `link`      | string | Link of the product.                                        |
| `image`     | string | Primary image of the product                                |
| `vendor`    | string | Vendor of the product (There is a vendor field inside meta) |
| `store_id`  | string | Store Id for the product.                                   |
| `aw_cat_id` | string | Warehouse category id.                                      |
| `metaItems` | array  | List of meta items (See Order - Product meta section).      |                                      |

### Order - Product meta ###

| Attribute   | Type   | Description                                          |
|-------------|--------|------------------------------------------------------|
| `sku_id`    | string | Title of the products.                               |
| `uid`       | string | Last name.                                           |
| `key`       | string | Company name.                                        |
| `price`     | string | Address line 1                                       |
| `qty`       | string | Address line 2                                       |
| `meta`      | string | City name.                                           |
| `aw_cat_id` | string | ISO code or name of the state, province or district. |
| `metaItems` | array  | List of meta items .                                 |                                      |

> Example of create an order:

```shell
curl -X POST https://example.com/wp-json/wc/v3/orders \
	-H "Authorization: Bearer %token%" \
	-H "Content-Type: application/json" \
	-d '{
  "payment_method": "bacs",
  "payment_method_title": "Direct Bank Transfer",
  "set_paid": true,
  "billing": {
    "first_name": "John",
    "last_name": "Doe",
    "address_1": "969 Market",
    "address_2": "",
    "city": "San Francisco",
    "state": "CA",
    "postcode": "94103",
    "country": "US",
    "email": "john.doe@example.com",
    "phone": "(555) 555-5555"
  },
  "shipping": {
    "first_name": "John",
    "last_name": "Doe",
    "address_1": "969 Market",
    "address_2": "",
    "city": "San Francisco",
    "state": "CA",
    "postcode": "94103",
    "country": "US"
  },
  "line_items": [
    {
      "product_id": 93,
      "quantity": 2
    },
    {
      "product_id": 22,
      "variation_id": 23,
      "quantity": 1
    }
  ],
  "shipping_lines": [
    {
      "method_id": "flat_rate",
      "method_title": "Flat Rate",
      "total": "10.00"
    }
  ]
}'
```
