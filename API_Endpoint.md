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
|200   |  OK |  {<br/>&nbsp;&nbsp;&nbsp;&nbsp; "user_id"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;: 214,<br/>&nbsp;&nbsp;&nbsp;&nbsp; "account_id": 2 <br/>&nbsp;&nbsp;&nbsp;&nbsp; "is_phone"&nbsp;&nbsp;: 1 <br/>&nbsp;&nbsp;&nbsp;&nbsp; "usage_datetime": "2021-08-26T20:14:16+09:00"<br/>}  | 
|400  |  Bad request |{<br/>&nbsp;&nbsp;&nbsp;&nbsp; "code"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;: 400,<br/>&nbsp;&nbsp;&nbsp;&nbsp; "message": "400 bad request",<br/>&nbsp;&nbsp;&nbsp;&nbsp; "fields"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;: <br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{ <br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;user_id   :[required], <br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;account_id:[required],<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;is_phone  :[required],<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;usage_datetime:[required]<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} <br/>}  |  
|401  |  Unauthorized |{<br/>&nbsp;&nbsp;&nbsp;&nbsp; "code"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;: 401,<br/>&nbsp;&nbsp;&nbsp;&nbsp; "message": "401 Unauthorized"<br/>}  | 
