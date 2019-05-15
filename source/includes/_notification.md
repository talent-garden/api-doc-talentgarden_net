# Notification
<aside class="warning-white">Authentication type: <b>Api Key</b></aside>
Notification REST API service allows you to get in touch with our members using different channels.

## Emails

### Send email with template
This endpoint allow you to send an email specifing an existing template.
Template is dynamically populated and every template required its own `template_data` object based on how the templated has been realized.

The API response returns 200 if the email can be queued to be sent.

```shell
curl https://api.talentgarden.net/notification/v1/emails/d-6e84a13f03a848d68985b2c4de89f29c \
  --request POST \
  --data '{
      "from": {
        "email": "info@talentgarden.net",
        "name": "Talent Garden"
      },
      "to": "davide.dattoli@talentgarden.com",
      "cc": ["davide.dattoli@talentgarden.com"],
      "bcc": ["davide.dattoli@talentgarden.com"],
      "categories": ["marketing", "newsletter"],
      "template_data": {
        "subject": "My subject",
        "text": "Hello world!"
      }
    }' \
  --header "Content-Type: application/json" \
```

> The above command returns JSON structured like this:

```json
{}
```

#### HTTP Request

`POST https://api.talentgarden.net/notification/v1/emails/:templateId`

#### URL Parameters

Parameter | Required | Description
--------- | ------- | -----------
templateId | true | the id of the template to use. Please get in touch with us if you are not sure which id to use.

#### Body Parameters

Parameter | Required | Description
--------- | ------- | -----------
from.email | true | the email address to use as sender. We only accept email addresses under <b>talentgarden.net</b> domain
from.name | false | the sender name
to | true | the recipient(s) of the email to be sent. In case of one recipient this value can is a string while if there are multiple recipients this value is an array of strings (email addresses)
categories | true | array of strings of how the email can be categorized. Ex: `marking` or `newsletter`
template_data | true | this object must contain all the data required from the template you are using. In order to use the template correctly we suggest to review how it has been built
cc | false | the recipient(s) of the email that must be in CC. In case of one recipient this value can is a string while if there are multiple recipients this value is an array of strings (email addresses)
bcc | false | the recipient(s) of the email that must be in BCC. In case of one recipient this value can is a string while if there are multiple recipients this value is an array of strings (email addresses)
