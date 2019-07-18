# Guest
Guest REST API service allows you to register one or more people that are visiting a campus member.

## Registrations
This endpoint allow you to create a new guest Registration.
When a Registration is created, the campus member receives three different notifications based on informations we know about him.
Notifications are: email, sms and slack.
For example: email notification is always sent because we always know the email address; sms notification is sent only if the user added his phone number in his profile; the slack notification is sent only for members that are part of the Slack's organization Talent Garden.

The API response describe which kind of notifications we were able to delivery to the campus member.

```shell
curl https://api.talentgarden.net/guest/v1/registrations \
  --request POST \
  --data '{
    "full_name": "Guest",
    "email": "guest@talentgarden.org",
    "looking_for": "member@talentgarden.org",
    "campus_name": "Tag Milano Calabiana",
    "newsletter": true,
    "guests_number": 2,
    "company_name": "Guest Company",
    "telephones": ["+393334455666"]
  }' \
  --header "Content-Type: application/json"
```

> The above command returns JSON structured like this:

```json
{
	"email": true,
	"sms": true,
	"slack": false
}
```

#### HTTP Request

`POST https://api.talentgarden.net/guest/v1/registrations`

#### Body Parameters

Parameter | Required | Description
--------- | ------- | -----------
full_name | true | the guest's full name
email | true | the guest's email address
looking_for | true | the campus member email address. This will be use to fetch the user and, if it exists, to delivery the email.
campus_name | true | the campus where the guest is. This name will be used in the notification message
newsletter | true | true if the user can be added in our newsletter otherwise false
guests_number | false | the additional guests number that are with the guest
company_name | false | the company name where the guest work
telephones | false | the phone numbers that will receive the SMS. For example: sending the value of this field as an array of two elements, both the numbers will receive the same SMS. Format each number with a '+' and a country code, e.g., +16175551212
latitude | false | the latitude where the device that the guest is using is
longitude | false | the longitude where the device that the guest is using is
altitude | false | the altitude where the device that the guest is using is

## Jump In
This endpoint allow you to create a new `jump in` guest.
Since this guest is not related to a campus member this endpoint does not send any kind of notifications but, if the user agrees, he can be added in our newsletter.

The API response returns an empty object if everything went well.

```shell
curl https://api.talentgarden.net/guest/v1/jump_in \
  --request POST \
  --data '{
    "full_name": "Guest",
    "email": "guest@talentgarden.org",
    "campus_name": "Tag Milano Calabiana",
    "newsletter": true
  }' \
  --header "Content-Type: application/json"
```

> The above command returns JSON structured like this:

```json
{}
```

#### HTTP Request

`POST https://api.talentgarden.net/guest/v1/jump_in`

#### Body Parameters

Parameter | Required | Description
--------- | ------- | -----------
full_name | true | the guest's full name
email | true | the guest's email address
campus_name | true | the campus where the guest is
newsletter | true | true if the user can be added in our newsletter otherwise false
latitude | false | the latitude where the device that the guest is using is
longitude | false | the longitude where the device that the guest is using is
altitude | false | the altitude where the device that the guest is using is
