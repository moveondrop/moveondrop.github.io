# Payment #

The payment API allows you to retrieve available payment gateways 
and gives ability to pay multiple invoices at once.


## Retrieve gateways ##

This API helps you to retrieve available gateways for payment.


### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">GET</i>
		<h6>/payment/gateways</h6>
	</div>
</div>

### Response ###

### PaymentGateways ###

| Attribute | Type   | Description            |
|-----------|--------|------------------------|
| `data`    | array  | List of PaymentGateway |

### PaymentGateway ###

| Attribute      | Type    | Description                      |
|----------------|---------|----------------------------------|
| `id`           | integer | Id of this gateway.              |
| `gateway_type` | enum    | Type of this gateway.            |
| `name`         | string  | Name of this gateway             |
| `fee`          | decimal | Additional fees for this gateway |
| `fee_type`     | enum    | Fee type of this gateway         |


> Example of retrieving payment gateways:

```shell
curl -X GET BASE_URL/api/v1/payment/gateways \
	-H "Authorization: Bearer %token%" \
	-H "Content-Type: application/json"
```

> JSON response example:

```json
{
  "data": [
    {
      "id": 5,
      "gateway_type": "wallet",
      "name": "Wallet Gateway",
      "slug": "wallet-gateway",
      "display_order": 0,
      "logo": null,
      "fee": 0,
      "fee_type": "fixed"
    }
  ]
}
```



## Pay invoices ##

This API helps you to make payment for multiple invoices.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">POST</i>
		<h6>/payment/:gatewayId/pay</h6>
	</div>
</div>

### Make payment properties ###

| Attribute  | Type    | Description                                  |
|------------|---------|----------------------------------------------|
| `invoices` | array   | List of invoiceObject                        |
| `amount`   | decimal | The amount you wants to pay for the invoices |

### invoiceObject ###

| Attribute   | Type    | Description                                                 |
|-------------|---------|-------------------------------------------------------------|
| `type`      | enum    | Type of this invoice.                                       |
| `id`        | integer | Id of the invoice.                                          |


#### Supported invoice type ####
- buy-and-ship
- ship-for-me

Type should be `buy-and-ship` if the given invoice is `BuyingInvoice`.
Otherwise, it will be `ship-for-me` for `ShipmentInvoice`

> Example of paying invoices:

```shell
curl -X GET BASE_URL/api/v1/payment/5/pay \
	-H "Authorization: Bearer %token%" \
	-H "Content-Type: application/json"
		-d '{
   "invoices": [
        {
            "id": 3189,
            "type": "buy-and-ship"
        }
    ],
    "amount": 10
}'
```

> JSON response example:

```json
{
  "message": "Successfully paid by wallet",
  "transaction_id": "TX637c35ef3f748",
  "have_redirect_url": false
}
```
