---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - Shell
  
toc_footers:
  - <a href='mailto:digital@talentgarden.org?subject=API key request'>Request an API key</a>

includes:
  - enrichment
  - sms
  - errors

search: true
---

# Introduction

Welcome to the Talent Garden API! You can use our API endpoints, which can offer to you a set of tools that you can use to build new products.

We have language bindings in Shell and you can view code examples in the dark area to the right.

# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "x-api-key: YOUR_API_KEY"
```

> Make sure to replace `YOUR_API_KEY` with your API key.

Talent Garden uses API keys to allow access to the API. You can request an API key <a href='mailto:digital@talentgarden.org?subject=API key request'>getting in touch with us</a>.

Talent Garden expects for the API key to be included in all API requests to the server in a header that looks like the following:

`x-api-key: YOUR_API_KEY`

<aside class="notice">
You must replace <code>YOUR_API_KEY</code> with your personal API key.
</aside>

Some of our API endpoints, like for example the <a href="/#enrichment">Enrichment API</a>, can be used client side after that the domain has been whitelisted from us.<br>
<a href="mailto:digital@talentgarden.org?subject=[API Request] domain whitelist">Click here</a> to submit a request to whitelist your domain specifying what you are developing and how this access can help you to speed up the development process or to improve the user experience.
