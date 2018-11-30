# Validation
The Validation API allow a data validation process that ensures the delivery of clean and clear data to the programs, applications and services using it. It checks for the integrity and validity of data in order to avoid human input mistakes.

## IBAN
This API endpoint allows you to automate IBAN validation and perform the following:

 * validate if an IBAN is valid using it’s check digits
 * validate if an IBAN has valid domestic bank code and account number check digits *
 * validate IBAN length for specific country
 * validate IBAN structure/formatting for specific country
 * validate IBAN characters ( check for non-alphanumeric characters )
 * validate if country code supports IBAN standard
 * identify the bank which issued the IBAN
 * identify the country and country code of an IBAN
 * identify address of the bank issued the IBAN
 * identify bank’s BIC code
 * identify bank’s SEPA support: B2B,COR1,SCC,SCT,SDD

*Bank Code and Account Number validations are performed for certain banks and countries only.

As you can see from the response in the dark area, the validation object is a structured object with different levels of validation. To simply the validation you can consider the root parameter `valid` that is `true` only if all the validation has been passed correctly, otherwise `false`.

```shell
curl "https://api.talentgarden.net/validation/v1/iban?iban=IT60X0542811101000000123456" \
  --header "x-api-key: YOUR_API_KEY"
```

> The above command returns JSON structured like this:

```json
{
	"valid": true,
	"bank_data": {
		"bic": "BEPOIT21",
		"branch": "SEDE DI BERGAMO",
		"bank": "B.POPDI BERGAMO-CRED.VARESINO FUS UNIONE DI BANCHE ITALIANE",
		"address": "PIAZZA VITTORIO VENETO, 8",
		"city": "BERGAMO",
		"state": "BG",
		"zip": "24122",
		"phone": null,
		"fax": null,
		"www": null,
		"email": null,
		"country": "Italy",
		"country_iso": "IT",
		"account": "000000123456",
		"bank_code": "05428",
		"branch_code": "11101"
	},
	"errors": [],
	"validations": {
		"chars": {
			"code": "006",
			"message": "IBAN does not contain illegal characters"
		},
		"account": {
			"code": "002",
			"message": "Account Number check digit is correct"
		},
		"iban": {
			"code": "001",
			"message": "IBAN Check digit is correct"
		},
		"structure": {
			"code": "005",
			"message": "IBAN structure is correct"
		},
		"length": {
			"code": "003",
			"message": "IBAN Length is correct"
		},
		"country_support": {
			"code": "007",
			"message": "Country supports IBAN standard"
		}
	},
	"sepa_data": {
		"SCT": "YES",
		"SDD": "YES",
		"COR1": "YES",
		"B2B": "YES",
		"SCC": "NO"
	}
}
```

This endpoint performs IBAN validation.

### HTTP Request

`GET https://api.talentgarden.net/validation/v1/iban?iban=:iban`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
iban | true | the IBAN you want to validate

### Codes
The `validation` object is composed from multiple objects and each one with its own code, this is codes map:

Code | Meaning | Description
--------- | ------- | -----------
001	| Validation Success |	IBAN Check digit is correct
002	| Validation Success |	Account Number check digit is correct
003	| Validation Success |	IBAN Length is correct
004	| Validation Success |	Account Number check digit is not performed for this bank or branch
005	| Validation Success |	IBAN structure is correct
006	| Validation Success |	IBAN does not contain illegal characters
007	| Validation Success |	Country supports IBAN standard
201	|Validation Failed	| Account Number check digit not correct
202	| Validation Failed |	IBAN Check digit not correct
203	| Validation Failed |	IBAN Length is not correct
205	| Validation Failed |	IBAN structure is not correct
206	| Validation Failed |	IBAN contains illegal characters
207	| Validation Failed |	Country does not support IBAN standard

<aside class="notice">
<a href="mailto:digital@talentgarden.org?subject=[API Request] Enrichment domain whitelist">Submit a request</a> to whitelist your app domain in order to use this API client side, like for example to autocomplete a form.
</aside>


## VAT
This API endpoint enabling you to validate VAT numbers and get company informations (if available).

The API's response will consist of a number of different properties containing information about your query, the respective company results and whether or not the validation was successful.

Since the address fields can have different structures or are missing at all (Germany & Spain), we decided to give back a normalized `address` object with all address fields separated. <br>
The `address` object is obtained from the `company_address` so if it is empty the `address` object will be empty as well.

```shell
curl "https://api.talentgarden.net/validation/v1/vat?vat=IT03340710981" \
  --header "x-api-key: YOUR_API_KEY"
```

> The above command returns JSON structured like this:

```json
{
	"valid": true,
	"database": "ok",
	"format_valid": true,
	"query": "IT03340710981",
	"country_code": "IT",
	"vat_number": "03340710981",
	"company_name": "TALENT GARDEN S.P.A",
	"company_address": "VIA MERANO 16 \n20127 MILANO MI\n",
	"address": {
		"street_number": "16",
		"route": "Via Merano",
		"locality": "Milano",
		"city": "MI",
		"country": "IT",
		"postal_code": "20127"
	}
}
```

This endpoint performs VAT number validation.

### HTTP Request

`GET https://api.talentgarden.net/validation/v1/vat?vat=:vat`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
vat | true | the VAT number with the 2-letter country code prefix

<aside class="notice">
<a href="mailto:digital@talentgarden.org?subject=[API Request] Enrichment domain whitelist">Submit a request</a> to whitelist your app domain in order to use this API client side, like for example to autocomplete a form.
</aside>
