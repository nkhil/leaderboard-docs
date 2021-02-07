---
description: Here's a reference for the Leaderboard API
---

# Leaderboard API docs

**←**👈 ****[**Back to Leaderboard API website**](www.google.com) ****

##  Client credentials

In order to generate valid client credentials, visit [https://leaderboardapi.com/dashboard](https://leaderboardapi.com/dashboard). You will need to sign up first

{% api-method method="get" host="https://api.leaderboardapi.com" path="/ping" %}
{% api-method-summary %}
GET api readiness
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{ "status": "OK" }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{ "status": "NOT OK" }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.leaderboardapi.com" path="/v1/token" %}
{% api-method-summary %}
Get Token
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to get an authorization token
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="x-api-key" type="string" required=true %}
Your API key
{% endapi-method-parameter %}

{% api-method-parameter name="x-client-secret" type="string" required=true %}
Your client secret
{% endapi-method-parameter %}

{% api-method-parameter name="x-client-id" type="string" required=true %}
Your client id
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Successfully generated auth token.
{% endapi-method-response-example-description %}

```
{ authToken: <your_auth_token_jwt> }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
Request lacks valid authentication credentials
{% endapi-method-response-example-description %}

```
{ "message": "Invalid Credentials" }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="" path="/team" %}
{% api-method-summary %}
POST team
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Bearer token JWT
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "teamName": "A Team",
  "id": "001456732910846354678",
  "createdAt": "",
  "modifiedAt": ""
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "message": "Not Authorized"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



