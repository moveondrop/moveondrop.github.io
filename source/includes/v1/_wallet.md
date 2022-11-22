# Wallet #

The Wallet API allows you to retrieve personal wallet information.


### Retrieve wallet balance ###

This API helps you to retrieve your personal wallet balance.


### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">GET</i>
		<h6>/customer/wallet/balance</h6>
	</div>
</div>


## Response ##

## WalletBalance ##

| Attribute      | Type    | Description                                        |
|----------------|---------|----------------------------------------------------|
| `current`      | decimal | Available balance to this wallet                   |
| `hold_balance` | decimal | The balance that is currently `in hold` by MoveOn. |
| `in_balance`   | decimal | Credited amount to this wallet in running month    |
| `out_balance`  | decimal | Debited amount from this wallet in running month   |

> Example of retrieving wallet balance:

```shell
curl -X GET https://moveon-api-server.sbox.ali2bd.net/api/v1/customer/wallet/balance \
	-H "Authorization: Bearer %token%" \
	-H "Content-Type: application/json"
```

> JSON response example:

```json
{
  "current": 1244.36,
  "hold_balance": 69,
  "in_balance": 0,
  "out_balance": 0
}
```
