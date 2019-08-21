# Customer
<aside class="warning-white">Authentication type: <b>Api Key</b></aside>

The Customer API service lets you to manage customer in our ERP. Customers will be transfer to TagPeople once a first Sales Order is created.

Talent Garden has two different types of customers: individuals and companies. Individuals may not have a VAT while it is mandatory for companies.

## Companies

### Create a Company
This endpoint allows you to create a new company as a Talent Garden customer.
The API creates a new customer only if the VAT doesn't exist otherwise the id of the existing customer is returned.

This endpoint creates or retrieves a Company customer.

#### HTTP Request

`POST https://api.talentgarden.net/customer/v1/companies`


```shell
curl https://api.talentgarden.net/customer/v1/companies \
  --request POST \
  --data '{
    "source": "SHOPIFY",
    "subsidiary_id": 1,
    "email": "info@talentgarden.com",
    "company_name": "Talent Garden S.p.A.",
    "vat_number": "IT03340710981",
    "fiscal_code": "03340710981",
    "first_name": "Davide",
    "last_name": "Dattoli",
    "sdi_code": "KUPCRMI",
    "pec_email": "talentgarden@pec.it",
    "phone": "+390282942387",
    "billing_address": {
      "address": "Via Merano 16",
      "country": "IT",
      "state": "MI",
      "city": "Milan",
      "zip": "20127"
    },
    "shipping_address": {
      "address": "Via Merano 16",
      "country": "IT",
      "state": "MI",
      "city": "Milan",
      "zip": "20127"
    }
  }' \
  --header "Content-Type: application/json"
```

#### URL Parameters

Parameter | Required | Description
--------- | ------- | -----------
source | true | the source of the new customer. Right now only `SHOPIFY` is allowed
subsidiary_id | true | the id of the subsidiary that must be associated to the new customer in the ERP
email | true | email address of a representative of the company
company_name | true | the name of the company
vat_number | true | the VAT number of the company
fiscal_code | false | the fiscal code of the company. This value is the VAT number without the first 2 characters (required for IT company)
first_name | true | the first_name of a representative of the company
last_name | true | the last_name of a representative of the company
sdi_code | false | the `SDI` code of the customer for elettronic invoicing (required for IT company)
pec_email | false | the pec email address of the customer for elettronic invoicing (required for IT company)
phone | false | the phone number of the physical person or a representative of the company
billing_address.address | true | address of the billing address associated to the individual
billing_address.country | true | country of the billing address associated to the company
billing_address.state | true | state of the billing address associated to the company
billing_address.city | true | city of the billing address associated to the company
billing_address.zip | true | zip of the billing address associated to the company
shipping_address.address | true | address of the shipping address associated to the company
shipping_address.country | true | country of the shipping address associated to the company
shipping_address.state | true | state of the shipping address associated to the company
shipping_address.city | true | city of the shipping address associated to the company
shipping_address.zip | true | zip of the shipping address associated to the company

## Individuals

### Create an Individual
This endpoint allows you to create a new individual as a Talent Garden customer.
The API creates a new customer only if the Fiscal Code doesn't exist otherwise the id of the existing customer is returned.

This endpoint creates or retrieves an Individual customer.

#### HTTP Request

`POST https://api.talentgarden.net/customer/v1/individuals`


```shell
curl https://api.talentgarden.net/customer/v1/individuals \
  --request POST \
  --data '{
    "source": "SHOPIFY",
    "subsidiary_id": 1,
    "email": "davide.dattoli@talentgarden.com",
    "vat_number": "IT03340710981",
    "fiscal_code": "DTTDVD80A01F205V",
    "first_name": "Davide",
    "last_name": "Dattoli",
    "sdi_code": "KUPCRMI",
    "pec_email": "talentgarden@pec.it",
    "phone": "+390282942387",
    "billing_address": {
      "address": "Via Merano 16",
      "country": "IT",
      "state": "MI",
      "city": "Milan",
      "zip": "20127"
    },
    "shipping_address": {
      "address": "Via Merano 16",
      "country": "IT",
      "state": "MI",
      "city": "Milan",
      "zip": "20127"
    }
  }' \
  --header "Content-Type: application/json"
```

#### URL Parameters

Parameter | Required | Description
--------- | ------- | -----------
source | true | the source of the new customer. Right now only `SHOPIFY` is allowed
subsidiary_id | true | the id of the subsidiary that must be associated to the new customer in the ERP
email | true | email address of the individual
fiscal_code | true | the fiscal code of the individual
vat_number | false | the VAT number of the individual
first_name | true | the first_name of the individual
last_name | true | the last_name of the individual
sdi_code | false | the `SDI` code of the customer for elettronic invoicing. Required if an italian `vat_number` is specified
pec_email | false | the pec email address of the customer for elettronic invoicing. Required if an italian `vat_number` is specified
phone | false | the phone number of the individual
billing_address.address | true | address of the billing address associated to the individual
billing_address.country | true | country of the billing address associated to the individual
billing_address.state | true | state of the billing address associated to the individual
billing_address.city | true | city of the billing address associated to the individual
billing_address.zip | true | zip of the billing address associated to the individual
shipping_address.address | true | address of the shipping address associated to the individual
shipping_address.country | true | country of the shipping address associated to the individual
shipping_address.state | true | state of the shipping address associated to the individual
shipping_address.city | true | city of the shipping address associated to the individual
shipping_address.zip | true | zip of the shipping address associated to the individual
