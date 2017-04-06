# Accounts

## The account object

```json
{
    "id": 1,
    "name" : "Account Name",
    "account_id": "A6UJ9A0004A4",
    "type": "Customer",
    "division": "Account Division",
    "phone" : 1234567890,
    "fax": 1234567890,
    "industry": "Drug & Alcohol",
    "status": "Active",
    "manager_id": "U6UJ9A00004V",
    "address_id": "U6UJ9A00004V",
    "created_at": "2012-10-12 13:50:50.0",
    "updated_at": "2016-11-04 19:27:25.0",
    "address": {
        "id": "U6UJ9A00004V",
        "description" : "",
        "line1": "123 Street Ave",
        "line2": "Suite 1C",
        "city": "North Kingstown",
        "state": "RI",
        "postal_code": "10309",
        "is_primary": true,
        "is_mailing": true,
        "created_at": "2012-10-12 13:50:50.0",
        "updated_at": "2016-11-04 19:27:25.0",
    },
    "manager": {
        "id": "U6UJ9A00004V",
        "title": "Account Manager",
        "username": "amanager",
        "region": null,
        "division": null,
        "department": "Sales & Marketing",
        "email": "amanager@dominiondiagnostics.com",
        "phone": "123456789",
        "direct": "1234567890",
        "home": null,
        "fax": null,
        "mobile": null,
        "first_name": "Account",
        "last_name": "Manager",
        "middle_name": "X",
        "prefix": null,
        "suffix": null,
        "full_name": "Account X. Manager",
        "created_at": "2012-10-12 13:50:50.0",
        "updated_at": "2016-11-04 19:27:25.0",
    }
}
```

The account object represents a single client. Listing accounts returns an abbreviated
response, while showing an individual account returns children assets, such as
address and manager.

Field | Type | Description
---------- | ------------ | -----------
id | integer | The Location ID
name | string | Account Name
account_id | string | SalesLogix Account ID
type | string | The type of account (Customer, Prospect, Vendor, etc)
division | string | Account division
phone | integer | Primary Phone number
fax | integer | Primary
status | string | Account Status
manager_id | string | SalesLogix ID of the manager
address_id | string | SalesLogix ID of the address
created_at | timestamp | When account was created
updated_at | timestamp | When account was last updated
address | [Address](#addresses) | Object representing the account address
manager | [User](#users) | Object representing the account manager

> Example Representation:


## Get All Accounts

```shell
curl "https://api.dominiondiagnostics.com/accounts"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name" : "Account Name",
    "account_id": "A6UJ9A0004A4",
    "type": "Customer",
    "division": "Account Division",
    "phone" : 1234567890,
    "fax": 1234567890,
    "industry": "Drug & Alcohol",
    "status": "Active",
    "manager_id": "U6UJ9A00004V",
    "address_id": "U6UJ9A00004V",
    "created_at": "2012-10-12 13:50:50.0",
    "updated_at": "2016-11-04 19:27:25.0"
  },
  {
    "id": 2,
    "name" : "Account Name",
    "account_id": "A6UJ9A0004A4",
    "type": "Customer",
    "division": "Account Division",
    "phone" : 1234567890,
    "fax": 1234567890,
    "industry": "Drug & Alcohol",
    "status": "Active",
    "manager_id": "U6UJ9A00004V",
    "address_id": "U6UJ9A00004V",
    "created_at": "2012-10-12 13:50:50.0",
    "updated_at": "2016-11-04 19:27:25.0"
  }
]
```

This endpoint retrieves all accounts.

### HTTP Request

`GET http://api.dominiondiagnostics.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
name | null | Search for accoutns by name
created_at_min | null | Show accounts created since date
created_at_max | null | Show accounts created before date
updated_at_min | null | Show accounts updated since date
updated_at_max | null | Show accounts created before date
status | 'ACTIVE' | Filter accounts by status
type | null | Filter accounts by type

## Get a Specific Account

```shell
curl "http://api.dominiondiagnostics.com/accounts/<id>"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
{
    "id": 1,
    "name" : "Account Name",
    "account_id": "A6UJ9A0004A4",
    "type": "Customer",
    "division": "Account Division",
    "phone" : 1234567890,
    "fax": 1234567890,
    "industry": "Drug & Alcohol",
    "status": "Active",
    "manager_id": "U6UJ9A00004V",
    "address_id": "U6UJ9A00004V",
    "created_at": "2012-10-12 13:50:50.0",
    "updated_at": "2016-11-04 19:27:25.0",
    "address": {
        "id": "U6UJ9A00004V",
        "description" : "",
        "line1": "123 Street Ave",
        "line2": "Suite 1C",
        "city": "North Kingstown",
        "state": "RI",
        "postal_code": "10309",
        "is_primary": true,
        "is_mailing": true,
        "created_at": "2012-10-12 13:50:50.0",
        "updated_at": "2016-11-04 19:27:25.0",
    },
    "manager": {
        "id": "U6UJ9A00004V",
        "title": "Account Manager",
        "username": "amanager",
        "region": null,
        "division": null,
        "department": "Sales & Marketing",
        "email": "amanager@dominiondiagnostics.com",
        "phone": "123456789",
        "direct": "1234567890",
        "home": null,
        "fax": null,
        "mobile": null,
        "first_name": "Account",
        "last_name": "Manager",
        "middle_name": "X",
        "prefix": null,
        "suffix": null,
        "full_name": "Account X. Manager",
        "created_at": "2012-10-12 13:50:50.0",
        "updated_at": "2016-11-04 19:27:25.0",
    }
}
```

This endpoint retrieves a specific account.

### HTTP Request

`GET http://api.dominiondiagnostics.com/accounts/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Account to retrieve
