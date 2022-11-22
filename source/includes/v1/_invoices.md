# Category #

The Category API allows you to retrieve categories and associated warehouse categories.


### Retrieve buying invoices ###

This API helps you to retrieve buying invoices.


### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">GET</i>
		<h6>/customer/buy-ship/invoices</h6>
	</div>
</div>

## Request ##

### Available query parameters ###

| Attribute  | Type   | Description        |
|------------|--------|--------------------|
| `page`     | string | See paging section |
| `per_page` | string | See paging section |

## Response ##

## BuyInvoices ##

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



## Get warehouse category ##

This API helps you to retrieve related warehouse categories for a category.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">GET</i>
		<h6>/customer/calculate-shipment-cost</h6>
	</div>
</div>

## Request ##

### Available query parameters ###

| Attribute       | Type    | Description                                                |
|-----------------|---------|------------------------------------------------------------|
| `unit_type`     | enum    | Unit type for shipment                                     |
| `shipping_type` | enum    | Shipping type for shipment                                 |
| `p_origin`      | enum    | Product origin country                                     |
| `category_id`   | integer | The category for which we want to get warehouse categories |

#### Supported unit_type ####
- kg
- piece

#### Supported shipping_type ####
- air
- ship

#### Supported p_origin ####
- CN

## Response ##

## WarehouseCategories ##

| Attribute | Type  | Description                    |
|-----------|-------|--------------------------------|
| `data`    | array | List of WarehouseCategoryItem. |

### WarehouseCategoryItem ###

| Attribute             | Type    | Description                                                                                                       |
|-----------------------|---------|-------------------------------------------------------------------------------------------------------------------|
| `id`                  | integer | Id of the warehouse category id(During the order placement, the attribute `aw_category_id` refers to this value). |
| `agent_warehouse_id`  | integer | Id of the warehouse.                                                                                              |
| `category_id`         | integer | Shipping category id.                                                                                             |
| `rate`                | decimal | Rate of this warehouse category.                                                                                  |
| `unit_type`           | enum    | Unit type of this warehouse category..                                                                            |
| `shipping_type`       | enum    | Shipping type of this warehouse category.                                                                         |
| `is_customs_included` | bool    | Weather custom cost included or not.                                                                              |
| `is_active`           | bool    | Is this category is active.                                                                                       |
| `t_and_c`             | integer | Term and conditions for this warehouse category.                                                                  |
| `commission`          | decimal | MoveOn commission for this warehouse category.                                                                    |
| `categoryPriceSlots`  | array   | Price slots for wholesale.                                                                                        |

> Example of retrieving shipping categories:

```shell
curl -X GET https://moveon-api-server.sbox.ali2bd.net/api/v1/customer/calculate-shipment-cost?unit_type=kg&shipping_type=air&category_id=3&p_origin=CN \
	-H "Authorization: Bearer %token%" \
	-H "Content-Type: application/json"
```

> JSON response example:

```json
{
  "data": [
    {
      "id": 6402,
      "agent_warehouse_id": 16,
      "category_id": 3,
      "rate": 1400,
      "unit_type": "kg",
      "shipping_type": "air",
      "is_customs_included": false,
      "is_active": true,
      "t_and_c": null,
      "commission": 10,
      "categoryPriceSlots": [
        {
          "id": 3830,
          "aw_category_id": 6402,
          "rate_per_unit": 1400,
          "min_amount": "1.00",
          "max_amount": "3.00",
          "commission": null
        }
      ],
      "warehouse": {
        "id": 16,
        "name": "M*************",
        "address": "广州市白云区。西槎路同雅东街59号。同德仓A5\nBaiyun District, Guangzhou City. 59 Tong Ya Dong Street, Xicha Road. Tongdecang A5",
        "contact_person": "Md Sakhoat Hosain",
        "contact_number": "18328558704",
        "shipping_mark": "MoveOn2",
        "instruction": "1. Please use green woven bag to pack the cartoon or we will charge 15RMB for packing charge.\n2. Shipping mark is must. without shipping mark on the box, we will not ship the product.\n3. Wrong declaration of items will not be tolerated.\n4. Update tracking code on time. Otherwise your products will not be shipped.\n5.Shipping Price will be changed If Tax or Freight charge increased.\n6. If product is below 3KG then additional 100-150gram will be added to the weight.",
        "open_time": "12:59:53",
        "close_time": "12:59:57",
        "company": {
          "name": "M*************"
        },
        "charge_repacking": null,
        "charge_inspection": null,
        "est_sh_time": "10 - 15 days",
        "est_sh_time_from": 10,
        "est_sh_time_to": 15
      }
    }
  ]
}
```
