# Rankle - Server
##REST APIs
This application provides a set of REST APIs for interacting with a database that stores information about users, groups, and players.

## /login
Handles user login requests. Accepts POST requests with JSON body in the following format:

```
{
    "username": "USERNAME",
    "password": "PASSWORD"
}
```
## /signup
Handles user signup requests. Accepts POST requests with JSON body in the following format:

```
{
    "username": "USERNAME",
    "password": "PASSWORD",
    "f_name": "FIRST_NAME",
    "l_name": "LAST_NAME"
}
```
## /add_group
Handles requests to add a new group to the database. Accepts POST requests with JSON body in the following format:

```
{
    "name": "GROUP_NAME",
    "userId": "USER_ID"
}
```
## /add_player
Handles requests to add a new player to a group. Accepts POST requests with JSON body in the following format:

```
{
    "name": "PLAYER_NAME",
    "position": "POSITION",
    "groupId": "GROUP_ID"
}
```
## /get_groups
Handles requests to retrieve all groups belonging to a particular user. Accepts GET requests with userId parameter in the query string.

## /get_players
Handles requests to retrieve all players belonging to a particular group. Accepts GET requests with groupId parameter in the query string.

## /delete_group
Handles requests to delete a group from the database. Accepts DELETE requests with groupId parameter in the query string.

## /delete_player
Handles requests to delete a player from a group. Accepts DELETE requests with playerId parameter in the query string.

## /upload
Handles file upload requests. Accepts POST requests with file attached in the request body. The file is stored in the database.
