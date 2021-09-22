# Zuri Chat DM (Room InfO)

Connect With Us: `developer@zuri.chat`
Zuri Chat is an open source slack clone. However, it offers a lot more functionality via a plugin system where each room can be provided by a different plugin provider.
​
## **Authentication**
this API does not require any authentication for use, 

## **Errors**
When an error occurs, you will receive an error object. Most of these error objects contain an error code and an error description so that your applications can more efficiently identify the problem.
​
If you get a 4xx response code, then you can assume that there is a bad request from your end. In this case, 
check the [Standard Error Responses](#standard-error-responses) for more context.
​
5xx errors suggest a problem on server's end.
​
​
​
## API methods:
- GET

## End Points:
base url: https://dm.zuri.chat/docs/v1
### /room-info
- **Endpoint**: copymessagelink?room-id ={room-id}
- **Method**: GET
- **Description**: This is used to retrieve information about a room. it returns the  **room_id**, **org_id**, **room_users_id** ,**created_at**, **description** and ** number_of_users**.  
#### parameters: 
| Name | Data type |
|--------|-------------|
| room_id (required)| string |


#### how to get a room info
- use the endpoint **https://dm.zuri.chat/api/v1/copymessagelink/**
- input the room_id parameters **https://dm.zuri.chat/api/v1/room-info?room_id={room_id}**
- it will return **room_id,org_id,created_id,description and number_of_users.**
***please note the createroom is a get method***


##### Example: 

```sh
https://dm.zuri.chat/api/v1/room-info?room_id=6146d126845b436ea04d102e
```
##### response:

```json
code:201
   {
  "room_id": "6146d126845b436ea04d102e",
  "org_id": "6145eee9285e4a18402074cd",
  "room_user_ids": [
    "6145fc9a285e4a18402074f4",
    "6146ce37845b436ea04d102d"
  ],
  "created_at": "2021-09-19T05:56:52.421948Z",
  "description": "This room contains the coversation between 6145fc9a285e4a18402074f4 and 6146ce37845b436ea04d102d only",
  "Number of users": "2"
}
```
```sh
Code: 500
 Description: bad request
{
  "status": 500,
  "message": "internal server error"
}
```

