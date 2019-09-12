# Tiktok-API (unofficial)

A reverse engineered API for the Tiktok application. Contains information about users. It shows a users followers, people they are following, and post information.

## Endpoints

### POST api/{loginWithUsername}

This endpoint allows you to log in to Tiktok with your username & password.

# Parameters

### Path parameters

Path Parameter | Description | 
------------ | -------------
{loginWithUsername} | The email you are using to sign in.

### Query string parameters

Query string paramater | Required/Optional | Description | Type |
------------ | ------------- |------------ | ------------- |
email | Required | The email address you are using to sign in. | String
password | Required | The password for your account. | String

# Sample Request

```js
curl -I -X POST "https://api.tiktokunofficial.org/api/{loginWithUsername('<email>', '<password>')}"
```
# Sample Response


```json
{
    "avatar_url":  "www.tiktok/username/profile_img,
    "birthday": "December 1, 1990",
    "can_be_found_by_phone": 562-323-9876,
    "email": "jonnybonny@gmail.com",
    "mobile": "562-323-3456",
    "new_user": 1
}
```
### Response definitions

The following table describes each item in the response.

Response Item | Description | Data type |
------------ | ------------- |------------ | 
avatar_url | The users profile image URL.| String
birthday | The users birthday. | String 
can_be_found_by_phone | The users phone number. | Integer
email | The users email adress. | String   
gender | The users gender. | Integer
new_user | Indicates if a user is new | Integer


## Example Error Response

```json
{
  "captcha": "captchaanswer",
  "description": "Account not found",
  "error-code": 404,
}
```


