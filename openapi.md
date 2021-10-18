# Qognition AI
This is a sample server Petstore server.  You can find out more about     Swagger at [http://swagger.io](http://swagger.io) or on [irc.freenode.net, #swagger](http://swagger.io/irc/).      For this sample, you can use the api key `special-key` to test the authorization     filters.

## Version: 1.0.0

### Terms of service
<http://swagger.io/terms/>

**Contact information:**  
apiteam@swagger.io  

**License:** [Apache 2.0](http://www.apache.org/licenses/LICENSE-2.0.html)

[Find out more about Swagger](http://swagger.io)
### /pet

#### PUT
##### Summary

Update an existing pet

##### Responses

| Code | Description |
| ---- | ----------- |
| 400 | Invalid ID supplied |
| 404 | Pet not found |
| 405 | Validation exception |

##### Security

| Security Schema | Scopes | |
| --- | --- | --- |
| petstore_auth | write:pets | read:pets |

#### POST
##### Summary

Add a new pet to the store

##### Responses

| Code | Description |
| ---- | ----------- |
| 405 | Invalid input |

##### Security

| Security Schema | Scopes | |
| --- | --- | --- |
| petstore_auth | write:pets | read:pets |

### /pet/findByStatus

#### GET
##### Summary

Finds Pets by status

##### Description

Multiple status values can be provided with comma separated strings

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| status | query | Status values that need to be considered for filter | Yes | [ string ] |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid status value |

##### Security

| Security Schema | Scopes | |
| --- | --- | --- |
| petstore_auth | write:pets | read:pets |

### /pet/findByTags

#### GET
##### Summary

Finds Pets by tags

##### Description

Muliple tags can be provided with comma separated strings. Use         tag1, tag2, tag3 for testing.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| tags | query | Tags to filter by | Yes | [ string ] |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid tag value |

##### Security

| Security Schema | Scopes | |
| --- | --- | --- |
| petstore_auth | write:pets | read:pets |

### /pet/{petId}

#### GET
##### Summary

Find pet by ID

##### Description

Returns a single pet

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| petId | path | ID of pet to return | Yes | long |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid ID supplied |
| 404 | Pet not found |

##### Security

| Security Schema | Scopes |
| --- | --- |
| api_key | |

#### POST
##### Summary

Updates a pet in the store with form data

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| petId | path | ID of pet that needs to be updated | Yes | long |

##### Responses

| Code | Description |
| ---- | ----------- |
| 405 | Invalid input |

##### Security

| Security Schema | Scopes | |
| --- | --- | --- |
| petstore_auth | write:pets | read:pets |

#### DELETE
##### Summary

Deletes a pet

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| api_key | header |  | No | string |
| petId | path | Pet id to delete | Yes | long |

##### Responses

| Code | Description |
| ---- | ----------- |
| 400 | Invalid ID supplied |
| 404 | Pet not found |

##### Security

| Security Schema | Scopes | |
| --- | --- | --- |
| petstore_auth | write:pets | read:pets |

### /pet/{petId}/uploadImage

#### POST
##### Summary

uploads an image

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| petId | path | ID of pet to update | Yes | long |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |

##### Security

| Security Schema | Scopes | |
| --- | --- | --- |
| petstore_auth | write:pets | read:pets |

### /store/inventory

#### GET
##### Summary

Returns pet inventories by status

##### Description

Returns a map of status codes to quantities

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |

##### Security

| Security Schema | Scopes |
| --- | --- |
| api_key | |

### /store/order

#### POST
##### Summary

Place an order for a pet

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid Order |

### /store/order/{orderId}

#### GET
##### Summary

Find purchase order by ID

##### Description

For valid response try integer IDs with value >= 1 and <= 10.         Other values will generated exceptions

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| orderId | path | ID of pet that needs to be fetched | Yes | long |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid ID supplied |
| 404 | Order not found |

#### DELETE
##### Summary

Delete purchase order by ID

##### Description

For valid response try integer IDs with positive integer value.         Negative or non-integer values will generate API errors

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| orderId | path | ID of the order that needs to be deleted | Yes | long |

##### Responses

| Code | Description |
| ---- | ----------- |
| 400 | Invalid ID supplied |
| 404 | Order not found |

### /user

#### POST
##### Summary

Create user

##### Description

This can only be done by the logged in user.

##### Responses

| Code | Description |
| ---- | ----------- |
| default | successful operation |

### /user/createWithArray

#### POST
##### Summary

Creates list of users with given input array

##### Responses

| Code | Description |
| ---- | ----------- |
| default | successful operation |

### /user/createWithList

#### POST
##### Summary

Creates list of users with given input array

##### Responses

| Code | Description |
| ---- | ----------- |
| default | successful operation |

### /user/login

#### GET
##### Summary

Logs user into the system

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| username | query | The user name for login | Yes | string |
| password | query | The password for login in clear text | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid username/password supplied |

### /user/logout

#### GET
##### Summary

Logs out current logged in user session

##### Responses

| Code | Description |
| ---- | ----------- |
| default | successful operation |

### /user/{username}

#### GET
##### Summary

Get user by user name

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| username | path | The name that needs to be fetched. Use user1 for testing.  | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid username supplied |
| 404 | User not found |

#### PUT
##### Summary

Updated user

##### Description

This can only be done by the logged in user.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| username | path | name that need to be updated | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 400 | Invalid user supplied |
| 404 | User not found |

#### DELETE
##### Summary

Delete user

##### Description

This can only be done by the logged in user.

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| username | path | The name that needs to be deleted | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 400 | Invalid username supplied |
| 404 | User not found |

### Models

#### Order

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| id | long |  | No |
| petId | long |  | No |
| quantity | integer |  | No |
| shipDate | dateTime |  | No |
| status | string | Order Status<br>_Enum:_ `"placed"`, `"approved"`, `"delivered"` | No |
| complete | boolean |  | No |

#### Category

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| id | long |  | No |
| name | string |  | No |

#### User

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| id | long |  | No |
| username | string |  | No |
| firstName | string |  | No |
| lastName | string |  | No |
| email | string |  | No |
| password | string |  | No |
| phone | string |  | No |
| userStatus | integer | User Status | No |

#### Tag

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| id | long |  | No |
| name | string |  | No |

#### Pet

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| id | long |  | No |
| category | object |  | No |
| name | string | _Example:_ `"doggie"` | Yes |
| photoUrls | [ string ] |  | Yes |
| tags | [ object ] |  | No |
| status | string | pet status in the store<br>_Enum:_ `"available"`, `"pending"`, `"sold"` | No |

#### ApiResponse

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| code | integer |  | No |
| type | string |  | No |
| message | string |  | No |
