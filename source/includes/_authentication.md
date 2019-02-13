# Authentication
Authentication method changes based on the APIs service you need to call.
Talent Garden uses two different types of authentication:

  1. <b>API Key</b>
  2. <b>JSON Web Token (JWT)</b>

In each API service main section (Guest, User, SMS) is described the authentication method required from that service.
Every API service supports only one type of authentication method, so if for example the User service requires JWT authentication does not accept API Key authentication.

Some of our API services, like for example the <a href="/#enrichment">Enrichment API</a>, can be used client side after that the domain has been whitelisted from us.<br>
<a href="mailto:digital@talentgarden.org?subject=[API Request] domain whitelist">Click here</a> to submit a request to whitelist your domain specifying what you are developing and how this access can help you to speed up the development process or to improve the user experience.


## API Key
> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "x-api-key: YOUR_API_KEY"
```

> Make sure to replace `YOUR_API_KEY` with your API key.

API key allows to access to some of our API services.
This kind of authentication is often used for server to server comminication because API Key does not expire. For this way we highly reccomend to not expose the API Key client-side.

You can request an API key <a href='mailto:digital@talentgarden.org?subject=API key request'>getting in touch with us</a>.

Talent Garden expects the API key to be included in all API requests to the server in a header that looks like the following:

`x-api-key: YOUR_API_KEY`

<aside class="notice">
You must replace <code>YOUR_API_KEY</code> with your personal API key.
</aside>

Your API keys carry many privileges, so be sure to keep them secure! 
Do not share your secret API keys in publicly accessible areas such as GitHub, client-side code, and so forth.

## JSON Web Token
> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: Bearer YOUR_JWT"
```

> Make sure to replace `YOUR_JWT` with your JWT.

JSON Web Token (JWT) authentication is used to call API Services personifying a specific logged user.
The JWT must be issued from one of our applications registered in our Auth0 tenants.

To make calls to the API, send the JWT in the Authorization HTTP header using the Bearer authentication scheme.
Talent Garden expects the JWT to be included in all API requests from the client in a header that looks like the following:

`Authorization: Bearer YOUR_JWT`

<aside class="notice">
You must replace <code>YOUR_JWT</code> a valid Auth0 issued token.
</aside>

You can request an Auth0 OAuth2 client <a href='mailto:digital@talentgarden.org?subject=Auth0 OAuth2 client request'>getting in touch with us</a>.
