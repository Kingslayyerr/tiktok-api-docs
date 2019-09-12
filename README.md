# Tiktok-API (unofficial)

## Free Analytics!

Love using Tiktok? 

*So do we!*

This free **API** allows you to gain a deeper understanding of your Tiktok metrics, analytics and data.

It shows a Tiktok users followers, people they are following, and other valuable post information. 

**Use Case:** A Tiktok user who wants to keep track of his or her statistics to measure their account performance over time.

# Getting Started

## Installation

Make sure you have the latest version of NPM installed

**run** this command in your terminal:
```unix
 npm i tiktok-api
```


# Endpoint

### POST api/{loginWithUsername}

This endpoint allows you to log in to Tiktok with your username & password.

# Parameters

### Path parameters

Path Parameter | Description | 
------------ | -------------
{loginWithUsername} | The username you are using to sign in.

### Query string parameters

Query string paramater | Required/Optional | Description | Type |
------------ | ------------- |------------ | ------------- |
username | Required | The username you are using to sign in. | String
password | Required | The password for your account. | String

# Sample Request

```js
api.loginWithUsername('<username>', '<password>')
  .then(res => console.log(res.data))
  .catch(console.log)

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
# Endpoint

### GET getUser/{id}

This endpoint allows you get a users ID.

# Parameters

### Path parameters

Path Parameter | Description | 
------------ | -------------
{id} | The id of the user you are searching for. |


# Sample Request

```js
api.getUser('<user_id>')
  .then(res => console.log(res.data.user))
  .catch(console.log);
```
# Sample Response


```json
{
    "aweme_count":  22,
    "favoriting_count": 4,
    "follower_count": 300,
    "following_count": 20,
    "total_favorited": 8,
    "follow_status": 1
}
```
### Response definitions

The following table describes each item in the response.

Response Item | Description | Data type |
------------ | ------------- |------------ | 
aweme_count | The number of videos the user has uploaded.| Integer
favoriting_count | The number of videos the user has liked | Integer 
follower_count | The amount of followers the user has. | Integer
following_count | The amount of users this users follows. | Integer   
total_favorited | The total number of likes this user has received. | Integer
follow_status | Indicates if you follow this user,1 if true 0 if false. | Integer

# Endpoint

### GET getPost/{id}

This endpoint allows you to retrieve a specific post by ID.

# Parameters

### Path parameters

Path Parameter | Description | 
------------ | -------------
{id} | The id of the post you are searching for. |


# Sample Request

```js
api.getPost('<user_id>')
  .then(res => console.log(res.data.aweme_detail))
  .catch(console.log);
```
# Sample Response


```json
{
    "author_user_id":  12343,
    "aweme_id": 3245,
    "aweme_type": 1,
    "create_time": 2019-09-12T20:52:25+00:00,
    "music": "Back in Black - ACDC",
    "prevent_download": False,
    "rate": 12
}
```
### Response definitions

The following table describes each item in the response.

Response Item | Description | Data type |
------------ | ------------- |------------ | 
author_user_id | The ID of the post author | String
aweme_id | The ID of the post | String 
aweme_type | The type of post. | Integer
create_time | The time the post was created (in seconds). | Integer   
music | The music used in this post. | MusicTrack
prevent_download | True if user cannot download the video. | Boolean
rate | Age rating for the video. | Integer





