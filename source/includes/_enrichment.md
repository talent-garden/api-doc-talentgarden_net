# Enrichment
The Enrichment API lets you look up person and company data based on an email or domain. For example, you could retrieve a person’s name, location and social handles from an email. Or you could lookup a company’s location, headcount or logo based on their domain name.

## Combined
A common use-case is looking up a person and company simultaneously based on a email address. To save you making two requests to do this, we offer a combined lookup API.

This endpoint expects an email address, and will return an object containing both the person and company (if found). A call to the combined lookup will only count as one API call.


```shell
curl "https://api.talentgarden.net/enrichment/v1/combined?email=davide.dattoli@talentgarden.org" \
  --header "x-api-key: YOUR_API_KEY"
```

> The above command returns JSON structured like this:

```json
{
	"options": {},
	"person": {
		"id": "1d5d98b6-7703-425c-8087-d04ea335216d",
		"name": {
			"fullName": "Davide Dattoli",
			"givenName": "Davide",
			"familyName": "Dattoli"
		},
		"email": "davide.dattoli@talentgarden.org",
		"gender": null,
		"location": "IT",
		"timeZone": "Europe/Vatican",
		"utcOffset": 1,
		"geo": {
			"city": null,
			"state": null,
			"stateCode": null,
			"country": "Italy",
			"countryCode": "IT",
			"lat": 41.87194,
			"lng": 12.56738
		},
		"bio": "The best way to predict the future is to invent it. - President of @TalentGardenen Shaping a new way of Work, Learn and Connect",
		"site": "http://www.davidedattoli.it",
		"avatar": "https://d1ts43dypk8bqh.cloudfront.net/v1/avatars/1d5d98b6-7703-425c-8087-d04ea335216d",
		"employment": {
			"domain": "talentgarden.org",
			"name": "Talent Garden",
			"title": "CEO, Talent Garden, Talent Garden",
			"role": "ceo",
			"seniority": "executive"
		},
		"facebook": {
			"handle": "davidedattoli"
		},
		"github": {
			"handle": null,
			"id": null,
			"avatar": null,
			"company": null,
			"blog": null,
			"followers": null,
			"following": null
		},
		"twitter": {
			"handle": "davidedattoli",
			"id": 14523150,
			"bio": "The best way to predict the future is to invent it. - President of @TalentGardenen Shaping a new way of Work, Learn and Connect",
			"followers": 10609,
			"following": 1331,
			"statuses": 19904,
			"favorites": 4179,
			"location": "Brescia ✈ Milan ✈ New York",
			"site": "http://www.davidedattoli.it",
			"avatar": "https://pbs.twimg.com/profile_images/2539077588/1h7p22673pueqyq9ds9k.png"
		},
		"linkedin": {
			"handle": "in/davidedattoli"
		},
		"googleplus": {
			"handle": null
		},
		"aboutme": {
			"handle": null,
			"bio": null,
			"avatar": null
		},
		"gravatar": {
			"handle": null,
			"urls": null,
			"avatar": null,
			"avatars": []
		},
		"fuzzy": false,
		"emailProvider": false,
		"indexedAt": "2018-11-10T03:40:25.307Z"
	},
	"company": {
		"id": "6b0524b2-9c2d-4988-990e-afd5492f1673",
		"name": "Talent Garden",
		"legalName": null,
		"domain": "talentgarden.org",
		"domainAliases": [
			"talentgarden.ie",
			"talentgarden.es",
			"talentgarden.at",
			"talentgarden.co",
			"talentgarden.co.uk"
		],
		"site": {
			"phoneNumbers": [],
			"emailAddresses": [
				"info@talentgarden.org"
			]
		},
		"category": {
			"sector": "Information Technology",
			"industryGroup": "Software & Services",
			"industry": "Internet Software & Services",
			"subIndustry": "Internet",
			"sicCode": "87",
			"naicsCode": "54"
		},
		"tags": [
			"Marketplace",
			"B2B",
			"B2C",
			"Internet"
		],
		"description": "Talent Garden creates campuses to empower digital tech communities and connect them globally: coworking space, digital training, and networking. Join us!",
		"foundedYear": null,
		"location": "Via Cipro, 66, 25124 Brescia BS, Italy",
		"timeZone": "Europe/Rome",
		"utcOffset": 1,
		"geo": {
			"streetNumber": "66",
			"streetName": "Via Cipro",
			"subPremise": null,
			"city": "Brescia",
			"postalCode": "25124",
			"state": "Lombardia",
			"stateCode": null,
			"country": "Italy",
			"countryCode": "IT",
			"lat": 45.5246905,
			"lng": 10.2104083
		},
		"logo": "https://logo.clearbit.com/talentgarden.org",
		"facebook": {
			"handle": "talentgarden",
			"likes": 57056
		},
		"linkedin": {
			"handle": "company/talent-garden"
		},
		"twitter": {
			"handle": "talentgardenen",
			"id": "1291422799",
			"bio": "The place for explorers and innovators. #TalentGarden",
			"followers": 2459,
			"following": 726,
			"location": "",
			"site": "http://t.co/B91DTO9Gge",
			"avatar": "https://pbs.twimg.com/profile_images/882185915665448965/8K9la42a_normal.jpg"
		},
		"crunchbase": {
			"handle": "organization/talent-garden"
		},
		"emailProvider": false,
		"type": "private",
		"ticker": null,
		"identifiers": {
			"usEIN": null
		},
		"phone": null,
		"metrics": {
			"alexaUsRank": null,
			"alexaGlobalRank": null,
			"employees": 75,
			"employeesRange": "51-250",
			"marketCap": null,
			"raised": 12990000,
			"annualRevenue": null,
			"estimatedAnnualRevenue": "$10M-$50M",
			"fiscalYearEnd": null
		},
		"indexedAt": "2018-10-25T06:47:29.859Z",
		"tech": [
			"mailchimp",
			"google_apps",
			"activecampaign",
			"google_tag_manager",
			"facebook_advertiser",
			"facebook_connect",
			"nginx",
			"wordpress",
			"google_maps",
			"youtube",
			"sumo",
			"piwik",
			"google_analytics",
			"hubspot"
		],
		"parent": {
			"domain": null
		}
	}
}
```

This endpoint retrieves all informations about a company.

### HTTP Request

`GET https://api.talentgarden.net/enrichment/v1/combined?email=:email`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
email | true | the person’s email address

<aside class="notice">
<a href="mailto:digital@talentgarden.org?subject=[API Request] Enrichment domain whitelist">Submit a request</a> to whitelist your app domain in order to use this API client side, like for example to autocomplete a form.
</aside>


## Company
The Company API allows you to look up a company by their domain. Alongside the domain you may also provide any additional attributes you have about the company, such as their company name or twitter handle. Including more detail will help us be more accurate when searching.


```shell
curl "https://api.talentgarden.net/enrichment/v1/companies?domain=talentgarden.org" \
  --header "x-api-key: YOUR_API_KEY"
```

> The above command returns JSON structured like this:

```json
{
	"id": "6b0524b2-9c2d-4988-990e-afd5492f1673",
	"name": "Talent Garden",
	"legalName": null,
	"domain": "talentgarden.org",
	"domainAliases": [
		"talentgarden.ie",
		"talentgarden.es",
		"talentgarden.at",
		"talentgarden.co",
		"talentgarden.co.uk"
	],
	"site": {
		"phoneNumbers": [],
		"emailAddresses": [
			"info@talentgarden.org"
		]
	},
	"category": {
		"sector": "Information Technology",
		"industryGroup": "Software & Services",
		"industry": "Internet Software & Services",
		"subIndustry": "Internet",
		"sicCode": "87",
		"naicsCode": "54"
	},
	"tags": [
		"Marketplace",
		"B2B",
		"B2C",
		"Internet"
	],
	"description": "Talent Garden creates campuses to empower digital tech communities and connect them globally: coworking space, digital training, and networking. Join us!",
	"foundedYear": null,
	"location": "Via Cipro, 66, 25124 Brescia BS, Italy",
	"timeZone": "Europe/Rome",
	"utcOffset": 1,
	"geo": {
		"streetNumber": "66",
		"streetName": "Via Cipro",
		"subPremise": null,
		"city": "Brescia",
		"postalCode": "25124",
		"state": "Lombardia",
		"stateCode": null,
		"country": "Italy",
		"countryCode": "IT",
		"lat": 45.5246905,
		"lng": 10.2104083
	},
	"logo": "https://logo.clearbit.com/talentgarden.org",
	"facebook": {
		"handle": "talentgarden",
		"likes": 57056
	},
	"linkedin": {
		"handle": "company/talent-garden"
	},
	"twitter": {
		"handle": "talentgardenen",
		"id": "1291422799",
		"bio": "The place for explorers and innovators. #TalentGarden",
		"followers": 2459,
		"following": 726,
		"location": "",
		"site": "http://t.co/B91DTO9Gge",
		"avatar": "https://pbs.twimg.com/profile_images/882185915665448965/8K9la42a_normal.jpg"
	},
	"crunchbase": {
		"handle": "organization/talent-garden"
	},
	"emailProvider": false,
	"type": "private",
	"ticker": null,
	"identifiers": {
		"usEIN": null
	},
	"phone": null,
	"metrics": {
		"alexaUsRank": null,
		"alexaGlobalRank": null,
		"employees": 75,
		"employeesRange": "51-250",
		"marketCap": null,
		"raised": 12990000,
		"annualRevenue": null,
		"estimatedAnnualRevenue": "$10M-$50M",
		"fiscalYearEnd": null
	},
	"indexedAt": "2018-10-25T06:47:29.859Z",
	"tech": [
		"mailchimp",
		"google_apps",
		"activecampaign",
		"google_tag_manager",
		"facebook_advertiser",
		"facebook_connect",
		"nginx",
		"wordpress",
		"google_maps",
		"youtube",
		"sumo",
		"piwik",
		"google_analytics",
		"hubspot"
	],
	"parent": {
		"domain": null
	}
}
```

This endpoint retrieves all informations about a company.

### HTTP Request

`GET https://api.talentgarden.net/enrichment/v1/companies?domain=:domain`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
domain | true | the company’s domain

<aside class="notice">
<a href="mailto:digital@talentgarden.org?subject=[API Request] Enrichment domain whitelist">Submit a request</a> to whitelist your app domain in order to use this API client side, like for example to autocomplete a form.
</aside>

## Person
The People API lets you retrieve social information associated with an email address, such as a person’s name, location and Twitter handle.

```shell
curl "https://api.talentgarden.net/enrichment/v1/people?email=davide.dattoli@talentgarden.org" \
  --header "x-api-key: YOUR_API_KEY"
```

> The above command returns JSON structured like this:

```json
{
	"options": {},
	"id": "1d5d98b6-7703-425c-8087-d04ea335216d",
	"name": {
		"fullName": "Davide Dattoli",
		"givenName": "Davide",
		"familyName": "Dattoli"
	},
	"email": "davide.dattoli@talentgarden.org",
	"gender": null,
	"location": "IT",
	"timeZone": "Europe/Vatican",
	"utcOffset": 1,
	"geo": {
		"city": null,
		"state": null,
		"stateCode": null,
		"country": "Italy",
		"countryCode": "IT",
		"lat": 41.87194,
		"lng": 12.56738
	},
	"bio": "The best way to predict the future is to invent it. - President of @TalentGardenen Shaping a new way of Work, Learn and Connect",
	"site": "http://www.davidedattoli.it",
	"avatar": "https://d1ts43dypk8bqh.cloudfront.net/v1/avatars/1d5d98b6-7703-425c-8087-d04ea335216d",
	"employment": {
		"domain": "talentgarden.org",
		"name": "Talent Garden",
		"title": "CEO, Talent Garden, Talent Garden",
		"role": "ceo",
		"seniority": "executive"
	},
	"facebook": {
		"handle": "davidedattoli"
	},
	"github": {
		"handle": null,
		"id": null,
		"avatar": null,
		"company": null,
		"blog": null,
		"followers": null,
		"following": null
	},
	"twitter": {
		"handle": "davidedattoli",
		"id": 14523150,
		"bio": "The best way to predict the future is to invent it. - President of @TalentGardenen Shaping a new way of Work, Learn and Connect",
		"followers": 10609,
		"following": 1331,
		"statuses": 19904,
		"favorites": 4179,
		"location": "Brescia ✈ Milan ✈ New York",
		"site": "http://www.davidedattoli.it",
		"avatar": "https://pbs.twimg.com/profile_images/2539077588/1h7p22673pueqyq9ds9k.png"
	},
	"linkedin": {
		"handle": "in/davidedattoli"
	},
	"googleplus": {
		"handle": null
	},
	"aboutme": {
		"handle": null,
		"bio": null,
		"avatar": null
	},
	"gravatar": {
		"handle": null,
		"urls": null,
		"avatar": null,
		"avatars": []
	},
	"fuzzy": false,
	"emailProvider": false,
	"indexedAt": "2018-11-10T03:40:25.307Z"
}
```

This endpoint retrieves all informations about a person.

### HTTP Request

`GET https://api.talentgarden.net/enrichment/v1/people?email=:email`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
email | true | the person’s email address

<aside class="notice">
<a href="mailto:digital@talentgarden.org?subject=[API Request] Enrichment domain whitelist">Submit a request</a> to whitelist your app domain in order to use this API client side, like for example to autocomplete a form.
</aside>
