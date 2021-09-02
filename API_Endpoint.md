```
POST   (v1/usage_status)
```
- This endpoint inserts the last usage time of user for both spiral place web version and application.
A purpose is to track an availability of each user.

`
1/ Header: Authorization (AWS access token)
`

`
2/ REQUEST BODY SCHEMA: application/json
`
| Field  | Type  |  Description | Additional |
|---|---|---|---|
|user_id   |  long |  User ID | requried  |
|account_id  | long  |  Account ID that user belong to | requried  |
|is_phone  |  int | If user access from phone app  |  requried |
|usage_datetime | string  |  Last usage datetime |  requried |

`
3/ RESPONSE
`
| Status  | Meaning  | Schema |
|---|---|---|
|200   |  OK |  none | 
|400  | Bad request  |  {"code": 401,\"reason": "","message": "401 Unauthorized"} | 
|401  |  Unauthorized | If user access from phone app  | 
