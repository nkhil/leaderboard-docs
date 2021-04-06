---
description: 'Leaderboard API lets you manage teams, scores and leaderboards'
---

# Leaderboard API docs

## Leaderboard API OpenAPI Spec

Get the most up-to-date Open API specification for leaderboard API here: [https://api.leaderboardapi.com/swagger](https://api.leaderboardapi.com/swagger) 

{% api-method method="get" host="https://api.leaderboardapi.com" path="/swagger" %}
{% api-method-summary %}
Swagger
{% endapi-method-summary %}

{% api-method-description %}
Get the latest up-t-date open api specification for the leaderboard API.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
openapi: 3.0.0
info:
  title: Leaderboard API
  description: A simple leaderboard API that helps manage teams, games and players.
  version: 1.0.0
servers:
  - url: http://api.example.com/v1
    description: Optional server description, e.g. Main (production) server
  - url: http://staging-api.example.com
    description: Optional server description, e.g. Internal staging server for testing
paths:
  /liveness:
    get:
      description: Returns the readiness of the service
      operationId: ping
      x-eov-operation-id: ping
      x-eov-operation-handler: healthcheck
      responses:
        "200":
          description: OK
          content:
            application/json:
              schema:
                properties:
                  status:
                    type: string
                    example: OK
        "401":
          $ref: "#/components/responses/401"
        "404":
          $ref: "#/components/responses/404"
        "500":
          $ref: "#/components/responses/500"
  
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Client credentials

In order to generate valid client credentials, visit [https://leaderboardapi.com/dashboard](https://leaderboardapi.com/dashboard) after you've signed up.

[Sign up to Leaderboard API here](https://leaderboardapi.com/sign-up)

{% api-method method="get" host="https://api.leaderboardapi.com" path="/liveness" %}
{% api-method-summary %}
Liveness
{% endapi-method-summary %}

{% api-method-description %}
Liveness probe endpoint to check if the API is online and live. 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{ "message": "OK" }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.leaderboardapi.com" path="/token" %}
{% api-method-summary %}
Token
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to get an authorization token
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
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

{% api-method method="get" host="https://api.leaderboardapi.com" path="/team/:id" %}
{% api-method-summary %}
Team
{% endapi-method-summary %}

{% api-method-description %}
Get a team \(by id\) or get all teams that belong to your client-id \(your client id is generated when you sign up and used to get a valid authorization token\).
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=false %}
teamId
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=false %}
Bearer token
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "teamName": "Greenbay Packers",
  "id": "001456732910846354678",
  "createdAt": "",
  "modifiedAt": ""
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://api.leaderboardapi.com" path="/leaderboard" %}
{% api-method-summary %}
Leaderboard
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://api.leaderboardapi.com" path="/team" %}
{% api-method-summary %}
Team
{% endapi-method-summary %}

{% api-method-description %}
Teams belong to leaderboards. You will need to create a leaderboard before creating teams.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Bearer token JWT
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="leaderboardId" type="string" required=true %}
leaderboard id the team belongs to
{% endapi-method-parameter %}

{% api-method-parameter name="teamName" type="string" required=true %}
team name
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
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

{% api-method method="put" host="" path="/v1/team/:id" %}
{% api-method-summary %}
Team
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
teamId associated with the team being PUT
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Bearer token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="team" type="object" required=true %}
team details you'd like to update
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="delete" host="" path="/v1/team/:id" %}
{% api-method-summary %}
Team
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
teamId
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=false %}
Bearer token
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
no response
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

{% api-method method="post" host="" path="/v1/leaderboard" %}
{% api-method-summary %}
Leaderboard
{% endapi-method-summary %}

{% api-method-description %}
Create a new leaderboard
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Bearer token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="teams" type="array" required=true %}
teams to add to the leaderboard
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "name": "leaderboard name",
  "id": "123789345678",
  "createdAt": "",
  "modifiedAt": ""
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

