# Category #

The Category API allows you to retrieve categories and associated warehouse categories.


## Retrieve categories ##

This API helps you to retrieve categories.


### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">GET</i>
		<h6>/customer/category-search</h6>
	</div>
</div>

### Request ###

### Available query parameters ###

| Attribute | Type   | Description    |
|-----------|--------|----------------|
| `q`       | string | Search keyword |


### Response ###

### Categories ###

| Attribute | Type  | Description           |
|-----------|-------|-----------------------|
| `data`    | array | List of CategoryItem. |

### CategoryItem ###

| Attribute   | Type         | Description                                                                     |
|-------------|--------------|---------------------------------------------------------------------------------|
| `id`        | integer      | Id of this category.                                                            |
| `parent_id` | integer/null | Parent category id of this category (null if category doesn't have any parent). |
| `name`      | string       | Name of this category.                                                          |
| `isLast`    | boolean      | Indicate weather this category have child or not(`false` if it has children)    |

> Example of retrieving categories:

```shell
curl -X GET https://moveon-api-server.sbox.ali2bd.net/api/v1/customer/category-search?q=laptop \
	-H "Authorization: Bearer %token%" \
	-H "Content-Type: application/json"
```

> JSON response example:

```json
{
  "data": [
    {
      "id": 3,
      "parent_id": 2,
      "name": "Laptops",
      "isLast": true
    },
    {
      "id": 12,
      "parent_id": 2,
      "name": "Laptop Display",
      "isLast": true
    },
    {
      "id": 19,
      "parent_id": 17,
      "name": "Laptop Battery",
      "isLast": true
    },
    {
      "id": 478,
      "parent_id": 464,
      "name": "Laptop Battery",
      "isLast": true
    }
  ]
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

### Request ###

### Available query parameters ###

| Attribute       | Type    | Description                                                   |
|-----------------|---------|---------------------------------------------------------------|
| `unit_type`     | enum    | Unit type for shipment                                        |
| `shipping_type` | enum    | Shipping type for shipment                                    |
| `p_origin`      | enum    | Product origin country                                        |
| `category_id`   | integer | The category id for which we want to get warehouse categories |

#### Supported unit_type ####
- kg
- piece

#### Supported shipping_type ####
- air
- ship

#### Supported p_origin ####
- CN

### Response ###

### WarehouseCategories ###

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
| `is_active`           | bool    | Is this category is active or not.                                                                                |
| `t_and_c`             | string  | Term and conditions for this warehouse category.                                                                  |                      |
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
      "categoryPriceSlots": [
        {
          "id": 3830,
          "aw_category_id": 6402,
          "rate_per_unit": 1400,
          "min_amount": "1.00",
          "max_amount": "3.00"
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
