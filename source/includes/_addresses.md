# Addresses

## The Address Object
```json
{
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
}
```

The address object represents a single address.

Field | Type | Description
---------- | ------------ | -----------
id | string | SalesLogix ID of the address
description | string | Extra description
line1 | string | Address Line 1
line2 | string | Address Line 2
city | string | City
state | string | State
postal_code | string | Postal Code
is_primary | boolean | If this address is the primary one
is_mailing | boolean | Is it a mailing address?
created_at | timestamp | When address was created
updated_at | timestamp | When address was last updated

## Fetch an address

```shell
curl "http://api.dominiondiagnostics.com/addresses/<address-id>"
    -H "Authorization: access-token"
```

```php
<?php
$address = $api->getAddress('<address-id>');
```

> The above command returns:

```json
{
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
}
```

This endpoint retrieves a specific account.
