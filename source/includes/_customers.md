# Customers

## Create Customer

```shell
curl "http://adleria.com/api/v1/customers"
  -u myusername:mypassword
```

```javascript
var adleria = require('adleria')('networkId', 'token');
adleria.customers.create()
````

### HTTP Request

`POST http://adleria.com/api/v1/customers`

### Body Parameters

Parameter | Description
--------- | -----------
company.VAT | Vat number.
company.email | Company email.
company.address.street | Company street.
company.address.city | Company City.
company.address.ZIP | Postal code.
company.address.country | Company country.
payoutInfo.IBAN | IBAN number
payoutInfo.BIC | BIC Number

## List Customers

```shell

curl "http://adleria.com/api/v1/customers"
  -u myusername:mypassword
```

```javascript

var adleria = require('adleria')('networkId', 'token');
adleria.customers.list()

```
> The above command returns JSON structured like this:

```json
[
  {
    "_id": "5673c3e029c704897b13e2fe",
    "networkId": "56695ea196a00b1a5ecf2ee8",
    "payoutInfo": {
      "currency": "EUR",
      "BIC": "1234",
      "IBAN": "1234"
    },
    "company": {
      "address": {
        "country": "Spain",
        "ZIP": "28703",
        "city": "Madrid",
        "street": "Jorge Juan 2"
      },
      "email": "email@email.com",
      "VAT": "1234",
      "name": "Company Name"
    }
  },
]
```

`GET http://adleria.com/api/v1/customers`
