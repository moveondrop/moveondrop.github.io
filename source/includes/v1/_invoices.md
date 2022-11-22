# Invoice #

The Invoice API allows you to retrieve invoices.


## Retrieve buying invoices ##

This API helps you to retrieve buying invoices.


### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">GET</i>
		<h6>/customer/buy-ship/invoices</h6>
	</div>
</div>

### Request ###

### Available query parameters ###

| Attribute  | Type   | Description              |
|------------|--------|--------------------------|
| `page`     | string | Page number              |
| `per_page` | string | Number of items per page |

### Response ###

### BuyInvoices ###

| Attribute | Type   | Description                        |
|-----------|--------|------------------------------------|
| `data`    | array  | List of BuyInvoice.                |
| `meta`    | object | See pagination section for detail. |

### BuyInvoice ###

| Attribute         | Type          | Description                           |
|-------------------|---------------|---------------------------------------|
| `id`              | integer       | Id of this buy invoice.               |
| `code`            | string        | Human readable invoice number.        |
| `total`           | decimal       | Total payable amount for this invoice |
| `paid_amount`     | decimal       | Total paid amount for this invoice    |
| `refunded_amount` | decimal       | Refunded amount for this invoice      |
| `status`          | enum          | Status of this invoice                |
| `paid_at`         | datetime/null | Payment completion time               |


> Example of retrieving buying invoices:

```shell
curl -X GET https://moveon-api-server.sbox.ali2bd.net/api/v1/customer/buy-ship/invoices \
	-H "Authorization: Bearer %token%" \
	-H "Content-Type: application/json"
```

> JSON response example:

```json
{
  "data": [
    {
      "id": 3189,
      "order_id": 5825,
      "code": "NV22215",
      "total": 2400,
      "paid_amount": 0,
      "refunded_amount": 0,
      "instructions": null,
      "invoice_to": null,
      "status": "unpaid",
      "paid_at": null,
      "status_label": "Unpaid",
      "settled_at": null,
      "is_overpaid": null,
      "created_at": "2022-11-21T23:31:14.000000Z"
    },
    {
      "id": 3188,
      "order_id": 5824,
      "code": "NV22214",
      "total": 2400,
      "paid_amount": 0,
      "refunded_amount": 0,
      "instructions": null,
      "invoice_to": null,
      "status": "unpaid",
      "paid_at": null,
      "status_label": "Unpaid",
      "settled_at": null,
      "is_overpaid": null,
      "created_at": "2022-11-21T16:02:55.000000Z"
    },
    {
      "id": 3187,
      "order_id": 5822,
      "code": "NV22213",
      "total": 160,
      "paid_amount": 0,
      "refunded_amount": 0,
      "instructions": null,
      "invoice_to": null,
      "status": "unpaid",
      "paid_at": null,
      "status_label": "Unpaid",
      "settled_at": null,
      "is_overpaid": null,
      "created_at": "2022-11-21T15:58:14.000000Z"
    },
    {
      "id": 3186,
      "order_id": 5821,
      "code": "NV22212",
      "total": 160,
      "paid_amount": 0,
      "refunded_amount": 0,
      "instructions": null,
      "invoice_to": null,
      "status": "unpaid",
      "paid_at": null,
      "status_label": "Unpaid",
      "settled_at": null,
      "is_overpaid": null,
      "created_at": "2022-11-21T15:56:20.000000Z"
    },
    {
      "id": 3185,
      "order_id": 5820,
      "code": "NV22211",
      "total": 160,
      "paid_amount": 0,
      "refunded_amount": 0,
      "instructions": null,
      "invoice_to": null,
      "status": "unpaid",
      "paid_at": null,
      "status_label": "Unpaid",
      "settled_at": null,
      "is_overpaid": null,
      "created_at": "2022-11-21T15:53:54.000000Z"
    }
  ],
  "links": {
    "first": "https://moveon-api-server.sbox.ali2bd.net/api/v1/customer/buy-ship/invoices?page=1",
    "last": "https://moveon-api-server.sbox.ali2bd.net/api/v1/customer/buy-ship/invoices?page=1",
    "prev": null,
    "next": null
  },
  "meta": {
    "current_page": 1,
    "from": 1,
    "last_page": 1,
    "links": [
      {
        "url": null,
        "label": "&laquo; Previous",
        "active": false
      },
      {
        "url": "https://moveon-api-server.sbox.ali2bd.net/api/v1/customer/buy-ship/invoices?page=1",
        "label": "1",
        "active": true
      },
      {
        "url": null,
        "label": "Next &raquo;",
        "active": false
      }
    ],
    "path": "https://moveon-api-server.sbox.ali2bd.net/api/v1/customer/buy-ship/invoices",
    "per_page": 10,
    "to": 5,
    "total": 5
  }
}
```


## Retrieve shipment invoices ##

This API helps you to retrieve shipment invoices.


### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">GET</i>
		<h6>/customer/invoices</h6>
	</div>
</div>

### Request ###

### Available query parameters ###

| Attribute  | Type   | Description              |
|------------|--------|--------------------------|
| `page`     | string | Page number              |
| `per_page` | string | Number of items per page |

### Response ###

### ShipmentInvoice ###

| Attribute | Type   | Description                        |
|-----------|--------|------------------------------------|
| `data`    | array  | List of ShipmentInvoice.           |
| `meta`    | object | See pagination section for detail. |

### ShipmentInvoice ###

| Attribute         | Type          | Description                           |
|-------------------|---------------|---------------------------------------|
| `id`              | integer       | Id of this shipment invoice.          |
| `invoice_code`    | string        | Human readable invoice number.        |
| `total`           | decimal       | Total payable amount for this invoice |
| `paid_amount`     | decimal       | Total paid amount for this invoice    |
| `refunded_amount` | decimal       | Refunded amount for this invoice      |
| `status`          | enum          | Status of this invoice                |
| `paid_at`         | datetime/null | Payment completion time               |


> Example of retrieving shipment invoices:

```shell
curl -X GET https://moveon-api-server.sbox.ali2bd.net/api/v1/customer/invoices\
	-H "Authorization: Bearer %token%" \
	-H "Content-Type: application/json"
```
