# Category #

The Category API allows you to retrieve shipping categories and associated warehouse categories.


## Retrieve shipping categories ##

This API helps you to retrieve shipping information.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">GET</i>
		<h6>/customer/category-search</h6>
	</div>
</div>

## Request ##

### Available query parameters ###

| Attribute | Type   | Description    |
|-----------|--------|----------------|
| `q`       | string | Search keyword |

## Response ##

## Categories ##

| Attribute | Type  | Description           |
|-----------|-------|-----------------------|
| `data`    | array | List of CategoryItem. |

### CategoryItem ###

| Attribute      | Type    | Description                                      |
|----------------|---------|--------------------------------------------------|
| `id`           | integer | Id of the category.                              |
| `parent_id`    | integer | Parent category id of this category.             |
| `name`         | string  | Name of this category.                           |
| `isLast`       | boolean | Indicate weather this category have child or not |

> Example of retrieving shipping categories:

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
