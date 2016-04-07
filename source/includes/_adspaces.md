# Adspaces

## Create Adspaces

```shell
curl "http://adleria.com/api/v1/adspaces"
  -u myusername:mypassword
  -d customerId:1234
  -d name:adspaceName
```

```javascript
var adleria = require('adleria')('networkId', 'token');
adleria.adspaces.create({
  name: 'adspace name',
  customerId: 'customerid'
})
```

> The above command returns JSON structured like this:

```json
{
  "slug": "",
  "networkId": "56695ea196a00b1a5ecf2ee8",
  "customerId": "5673c3e029c704897b13e2fe",
  "_id": "56cdda87946181c38d1116df",
  "status": "new",
  "review": {
    "reviewDate": null,
    "reason": "",
    "approved": false
  },
  "images": [],
  "openHours": {
    "closeTime": "18:00",
    "openTime": "9:00"
  },
  "restricted": [],
  "price": {
    "currency": "EUR",
    "netto": 0
  },
  "players": [],
  "targets": [],
  "rating": {
    "fixed": false,
    "current": 1
  },
  "type": "video/audio",
  "creationDate": "2016-02-24T16:29:44.249Z",
  "location": {
    "country": "",
    "ZIP": "",
    "city": "",
    "street2": "",
    "street": ""
  },
  "description": "",
  "name": ""
}
```

### HTTP Request

`POST http://adleria.com/api/v1/adspaces`

### Body Parameters

Param | Description
-------------- | -------------- 
customerId *required* | Customer id of the adspace owner
name *optional* | Name of the adspace, between 3 and 50 characters.
description *optional* | Description of the adspace. Maximum 250 characters.
location.city *optional* | City of the adspace.
location.country *optional* | Country of the adspace.
location.street *optional* | Street of the adspace.
location.lat *optional* | Number with adspace latitude.
location.lng *optional* | Number with adspace longitude.
type *optional* | Type of adspace content. "video", "video/audio" or "audio". Defaults to "video/audio".
targets *optional* | Array with target ids. See Tags to get targets information.
estimatedMonthlyVisitors *optional* | Number with estimated monthly adspace visitors.
price.netto *optional* | Price per add in the adspace in cents.
openHours.openTime *optional* | String with adspace openning hour. Defaults to "9:00"
openHours.closeTime *optional* | String with adspace closing hour. Defaults to "9:00"
images *optional* | Array with a list of images. Images has this properties {src: "", title: "", previewUrl: "", thumbnail:""}

## List Adspaces

```shell

curl "http://adleria.com/api/v1/adspaces"
  -u myusername:mypassword
```

```javascript

var adleria = require('adleria')('networkId', 'token');
adleria.adspaces.list()

```
> The above command returns JSON structured like this:

```json
{
  "count": "1",
  "docs": [
    {
      "_id": "56ab710f282fc95a566b25cf",
      "slug": "holasfdsf",
      "customerId": "56ab6f3bda834faa54ba4bfc",
      "networkId": "56695ea196a00b1a5ecf2ee8",
      "status": "new",
      "review": {
        "reviewDate": "2016-02-16T09:20:46.156Z",
        "reason": "",
        "approved": true
      },
      "images": [],
      "openHours": {
        "closeTime": "18:00",
        "openTime": "9:00"
      },
      "restricted": [],
      "price": {
        "currency": "EUR",
        "netto": 0
      },
      "players": [],
      "targets": [
        "56695e59b8cc27d35dcb0627",
        "56695e59b8cc27d35dcb062c",
        "56695e59b8cc27d35dcb0629"
      ],
      "rating": {
        "fixed": false,
        "current": 1
      },
      "type": "video/audio",
      "creationDate": "2016-01-29T14:02:33.501Z",
      "location": {
        "country": "",
        "ZIP": "",
        "city": "",
        "street2": "",
        "street": ""
      },
      "description": "",
      "name": "holasfdsf"
    }
  ]
}
```

Retrieve a list with all adspaces. Optionaly a customer can be set to get only that customer adspaces.

### Query parameters

Param | Description
-------------- | -------------- 
customerId *optional* | Get only adspaces for this customer
limit *optional* | Limit of adspaces to retrieve. Default 10.

## Get Adspace
```shell

curl "http://adleria.com/api/v1/adspaces/{adspaceId}" \
  -u myusername:mypassword 
```

```javascript

var adleria = require('adleria')('networkId', 'token');
adleria.adspaces.get({adspaceId});

```
Get Adspace details.

### HTTP Request

`GET http://adleria.com/api/v1/adspaces/{adspaceId}`

## Edit Adspace
```shell

curl "http://adleria.com/api/v1/adspaces/adspaceId" \
  -u myusername:mypassword \
  -d {param:value}
```

```javascript

var adleria = require('adleria')('networkId', 'token');
adleria.adspaces.edit({adspaceId}, {args});

```
> The above command returns JSON structured like this:

```json
{
  "_id": "56ab710f282fc95a566b25cf",
  "slug": "holasfdsf",
  "customerId": "56ab6f3bda834faa54ba4bfc",
  "networkId": "56695ea196a00b1a5ecf2ee8",
  "status": "new",
  "review": {
    "reviewDate": "2016-02-16T09:20:46.156Z",
    "reason": "",
    "approved": true
  },
  "images": [],
  "openHours": {
    "closeTime": "18:00",
    "openTime": "9:00"
  },
  "restricted": [],
  "price": {
    "currency": "EUR",
    "netto": 0
  },
  "players": [],
  "targets": [],
  "rating": {
    "fixed": false,
    "current": 1
  },
  "type": "video/audio",
  "creationDate": "2016-01-29T14:02:33.501Z",
  "location": {
    "country": "",
    "ZIP": "",
    "city": "",
    "street2": "",
    "street": ""
  },
  "description": "",
  "name": "holasfdsf"
}

```
Edit adspace and returns the edited adspace.
### HTTP Request

`PUT http://adleria.com/api/v1/adspaces/{adspaceId}`