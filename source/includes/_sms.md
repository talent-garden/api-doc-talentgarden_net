# SMS
Using SMS REST API, you can send outgoing SMS messages from an alphanumeric sender ID identifier to mobile phones around the globe.

An alphanumeric sender ID of up to 11 characters can be used for sending messages. To use an alphanumeric sender ID for sending messages, input your ID in the `from` parameter of your API request.
Alphanumeric Sender ID messages are one-way only, as users will be unable to directly reply to messages not sent from a phone number.


## Message
This endpoint allow you to send a new outgoing message from an alphanumeric ID to an outside number.

```shell
curl https://api.talentgarden.net/sms/v1/messages \
  --request POST \
  --data '{"from": "TagMilan","to": "+393334455666", "body": "Hi there, someone is waiting for you at the reception", "country": "IT"}' \
  --header "Content-Type: application/json" \
  --header "x-api-key: YOUR_API_KEY"
```

> The above command returns JSON structured like this:

```json
{
	"accountSid": "ACe216cab89d888c5cb280335ef76df4c3",
	"apiVersion": "2010-04-01",
	"body": "Hi there, someone is waiting for you at the reception",
	"dateCreated": "2018-11-27T10:18:00.000Z",
	"dateUpdated": "2018-11-27T10:18:00.000Z",
	"dateSent": null,
	"direction": "outbound-api",
	"errorCode": null,
	"errorMessage": null,
	"from": "TagMilan",
	"messagingServiceSid": null,
	"numMedia": "0",
	"numSegments": "1",
	"price": null,
	"priceUnit": "USD",
	"sid": "SM82743a9aab8f47259529a0776fe45eb4",
	"status": "queued",
	"subresourceUris": {
		"media": "/2010-04-01/Accounts/ACe216cab89d888c5cb280335ef76df4c3/Messages/SM82743a9aab8f47259529a0776fe45eb4/Media.json"
	},
	"to": "+393334455666",
	"uri": "/2010-04-01/Accounts/ACe216cab89d888c5cb280335ef76df4c3/Messages/SM82743a9aab8f47259529a0776fe45eb4.json"
}
```

### HTTP Request

`POST https://api.talentgarden.net/sms/v1/messages`

### Body Parameters

Parameter | Required | Description
--------- | ------- | -----------
from | true | this must be an alphanumeric ID
to   | true | this parameter determines the destination phone number for your SMS message. Format this number with a '+' and a country code, e.g., +16175551212 <a href="https://en.wikipedia.org/wiki/List_of_country_calling_codes" target="_blank">(E.164 format)</a>
body | true | the full text of the message you want to send. If the body of your message is more than 160 characters, we will send the message as a segmented SMS
country | true | the ISO country code where is the campus that is sending the SMS. Right now only `IT` is allowed
