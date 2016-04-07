# Payout Orders
  Payout orders are reverse invoice with payments made from adleria to customers and networks.
## List Payout Orders

Retrieve a list with payout orders. Optionaly a customer can be set to get only that customer adspaces.

### Query parameters
Param | Description
-------------- | -------------- 
customerId *optional* | Get only adspaces for this customer
limit *optional* | Limit of adspaces to retrieve. Default 10.

```shell
curl "http://adleria.com/api/v1/payout-orders"
  -u myusername:mypassword
```

```javascript
var adleria = require('adleria')('networkId', 'token');
adleria.payoutOrders.list()
````

### HTTP Request

`GET http://adleria.com/api/v1/payout-orders`

## Get Payout Order

```shell
curl "http://adleria.com/api/v1/payout-orders/{payoutOrderId}"
  -u myusername:mypassword
```

```javascript
var adleria = require('adleria')('networkId', 'token');
adleria.payoutOrders.get({payoutorderId})
````

### HTTP Request

`GET http://adleria.com/api/v1/payout-orders/{payoutOrderId}`