# <u>API docs</u>
- 目次
  - signup
  - login
  - Update user
  - Delete user
  - Get timeline
  - Get users
  - Get user todo_tweet
  - Get followee
  - Get follower
  - Get todo_tweet
  - Post todo_tweet
  - Update todo_tweet API
  - Delete todo_tweet API

## <u>Signup API</u>
- ユーザーが新規登録する際のAPI

### Mehod/Endpoint
```http
POST /signup
```

### Request body
|key|value|
|---|---|
|user_name|user_name_hoge|
|user_password|user_password_hoge|

## <u>Login API</u>
- ユーザーがログインする際のAPI

### Mehod/Endpoint
```http
POST /signup
```

### Request body
|key|value|
|---|---|
|user_name|user_name_hoge|
|user_password|user_password_hoge|

### Response Header
```http
Authorization: Bearer/JWT
```

## <u>Update user API</u>
- ユーザー情報を変更するためのAPI

### Mehod/Endpoint
```http
PUT /api/v1/user
```

### Request Header
```http
Authorization: Bearer/JWT
```

### Request body
|key|value|
|---|---|
|user_name|user_name_update|
|user_password|user_password_update|
|user_description|user_description_update|

## <u>Delete user API</u>
- ユーザー情報を削除するためのAPI

### Mehod/Endpoint
```http
DLETE /api/v1/user
```

### Request Header
```http
Authorization: Bearer/JWT
```

## <u>Get timeline API</u>
- ログインユーザー、followeeのtodo_tweetを表示する際のAPI

### Mehod/Endpoint
```http
GET /api/v1/timeline
```

### Query Parametes
```http
?offset=0
```

### Request Header
```http
Authorization: Bearer/JWT
```

### Response Header
```http
Content-Type: Application/json
```
### Response body
```json
{
  "todo_tweets": [
    {
      "todo_id":1,
      "todo":"todo_hgoe",
      "done":"false",
      "created_at":"2020-01-01 00:00:00",
      "user_name":"usr_name_hoge",
    },
    {
      "todo_id":2,
      "todo":"todo_fuga",
      "done":"false",
      "created_at":"2020-01-10 00:00:00",
      "user_name":"usr_name_fuga",
    }
  ]
}
```

## <u>Get users API</u>
- followeeを探すためにユーザー一覧を表示させる際のAPI

### Mehod/Endpoint
```http
GET /api/v1/users
```

### Query Parametes
```http
?offset=0
```

### Request Header
```http
Authorization: Bearer/JWT
```

### Response Header
```http
Content-Type: Application/json
```
### Response body
```json
{
  "usr_name": [
    "user_name_hoge",
    "user_name_fuga",
  ]
}
```

## <u>Get user todo_tweet API</u>
- 該当のユーザー情報とtodo_tweetを表示させる際のAPI

### Mehod/Endpoint
```http
GET /api/v1/user
```

### Query Parametes
```http
?offset=0
```

### Request Header
```http
Authorization: Bearer/JWT
```

### Response Header
```http
Content-Type: Application/json
```
### Response body
```json
{
  "user": {
    "user_name":"user_name_hoge",
    "user_description":"user_description_hoge",
  },
  "todo_tweet":[
    {
      "todo_id":1,
      "todo":"todo_hgoe",
      "done":"false",
      "created_at":"2020-01-01 00:00:00",
    },
    {
      "todo_id":2,
      "todo":"todo_fuga",
      "done":"false",
      "created_at":"2020-01-10 00:00:00",
    }
  ]
}
```

## <u>Get followee API</u>
- 該当ユーザーのfolloweeを表示する際のAPI


### Mehod/Endpoint
```http
GET /api/v1/followee
```

### Query Parametes
```http
?offset=0
```

### Request Header
```http
Authorization: Bearer/JWT
```

### Response Header
```http
Content-Type: Application/json
```
### Response body
```json
{
  "followees": [
    {
      "user_name":"user_name_hoge",
      "user_description":"user_description_hoge",
      "created_at":"2020-01-01 00:00:00",
    },
    {
      "user_name":"user_name_fuga",
      "user_description":"user_description_fuga",
      "created_at":"2020-01-10 00:00:00",
    }
  ]
}
```

## <u>Get follower API</u>
- 該当ユーザーのfollowerを表示する際のAPI


### Mehod/Endpoint
```http
GET /api/v1/follower
```

### Query Parametes
```http
?offset=0
```

### Request Header
```http
Authorization: Bearer/JWT
```

### Response Header
```http
Content-Type: Application/json
```
### Response body
```json
{
  "followers": [
    {
      "user_name":"user_name_hoge",
      "user_description":"user_description_hoge",
      "created_at":"2020-01-01 00:00:00",
    },
    {
      "user_name":"user_name_fuga",
      "user_description":"user_description_fuga",
      "created_at":"2020-01-10 00:00:00",
    }
  ]
}
```






## <u>Get todo_tweet API</u>
- 該当のtodo_tweetを表示する際のAPI

### Mehod/Endpoint
```http
GET /api/v1/todo
```

### Path Parametes
```http
todo_id
```

### Request Header
```http
Authorization: Bearer/JWT
```

### Response Header
```http
Content-Type: Application/json
```
### Response body
```json
{
  "todo_tweet":[
    {
      "todo_id":1,
      "todo":"todo_hgoe",
      "done":"false",
      "created_at":"2020-01-01 00:00:00",
    },
  ]
}
```

## <u>Post todo_tweet API</u>
- ログインユーザーがtodo_tweetを新規作成する際のAPI

### Mehod/Endpoint
```http
POST /api/v1/todo
```

### Path Parametes
```http
todo_id
```

### Request Header
```http
Authorization: Bearer/JWT
```

### Request body
|key|value|
|---|---|
|todo|todo_hoge|

## <u>Update todo_tweet API</u>
- ログインユーザーがtodo_tweetを更新する際のAPI

### Mehod/Endpoint
```http
PUT /api/v1/todo
```

### Path Parametes
```http
todo_id
```

### Request Header
```http
Authorization: Bearer/JWT
```

### Request body
|key|value|
|---|---|
|todo|tood_hoge_update|
|done|true|

## <u>Delete todo_tweet API</u>
- ログインユーザーがtodo_tweetを削除する際のAPI

### Mehod/Endpoint
```http
DELETE /api/v1/todo
```

### Path Parametes
```http
todo_id
```

### Request Header
```http
Authorization: Bearer/JWT
```
