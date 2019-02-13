# User
<aside class="warning-white">Authentication type: <b>JSON Web Token</b></aside>
The User API service lets you to manage different types of user entities. Right now only Members are available.

## Members

### Get member profile
This endpoint allow you to retrieve user profile information that, for example, can be used to personalize the experience of people interacting with your App.

```shell
curl "https://api.talentgarden.net/user/v1/members/:auth0_id/profile" \
  --header "Authentication: Bearer YOUR_JWT"
```

> The above command returns JSON structured like this:

```json
{
	"id": 3763,
	"email": "davide.dattoli@talentgarden.org",
	"first_name": "Davide",
	"last_name": "Dattoli",
	"picture_url": "https://talentgarden.org/davide.png",
	"biography": "Help people succeed",
	"title": "CEO",
	"enabled": true,
	"deleted": false,
	"telephones": [{
		"id": 789,
		"prefix": "39",
		"number": "3332345678"
	}],
	"customers": [{
		"id": 45,
		"name": "Talent Garden S.p.A",
		"credits": {
			"free": 1470,
			"paid": 0
		}
	}],
	"privacy_consent": true,
	"marketing_consent": false,
	"profiling_consent": true,
	"branches": [{
			"id": 22,
			"name": "Talent Garden S.p.A",
			"logo_url": "https://people.talentgarden.org/uploads/images/logo.png",
			"cover_url": "https://people.talentgarden.org/uploads/images/cover.jpeg",
			"members_count": 1,
			"registration_wizard_completed": true,
			"has_approved_subscription": true,
			"content_types": [
				"post",
				"idea_entity",
				"event",
				"project",
				"workgroup",
				"idea",
				"media",
				"request_offer"
			],
			"new_content_types": [{
					"type": "post",
					"filtering_type": "post"
				},
				{
					"type": "idea_entity",
					"filtering_type": "idea_entity"
				},
				{
					"type": "event",
					"filtering_type": "event"
				},
				{
					"type": "project",
					"filtering_type": "project"
				},
				{
					"type": "workgroup",
					"filtering_type": "workgroup"
				},
				{
					"type": "idea",
					"filtering_type": "idea"
				},
				{
					"type": "media",
					"filtering_type": "media"
				},
				{
					"type": "request_offer",
					"filtering_type": "request_offer"
				}
			],
			"share_data_consent": null
		}
	],
	"skills": [{
			"id": 165,
			"name": "Software Engineering"
		},
		{
			"id": 227,
			"name": "Databases"
		},
		{
			"id": 1405,
			"name": "Scalability"
		}
	],
	"interests": [{
			"id": 55,
			"name": "Technology"
		},
		{
			"id": 65,
			"name": "Photography"
		},
		{
			"id": 123,
			"name": "Software Design"
		}
	]
}
```

This endpoint retrieves all informations member profile.

#### HTTP Request

`GET https://api.talentgarden.net/user/v1/members/:auth0_id/profile`

#### URL Parameters

Parameter | Required | Description
--------- | ------- | -----------
auth0_id | true | the Auth0 identifier in the form "auth0&#124;identifier". This value is contained in the key `sub` of the JWT
