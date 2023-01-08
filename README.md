# Rankle - Server
## REST API
This application provides a set of REST APIs for interacting with a database that stores information about users, groups, and players.
This app is written completley in Python and Flask

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

## Randomization Functions

This script contains three functions for randomizing a list of players into groups.

## `randomize_players`

This function takes in two arguments:
- `active_players`: a list of player objects
- `size`: an integer representing the desired size of each group

It returns a tuple containing:
- a list of lists, where each inner list represents a group of players
- a list of players that were not included in any of the groups due to an uneven number of players

This function creates groups of players by selecting random players from the `active_players` list and adding them to a group until the desired group size is reached. Any remaining players that do not fit evenly into the groups are added to the `other` list and returned along with the list of groups.

## `randomize_by_rank`

This function also takes in two arguments:
- `active_players`: a list of player objects
- `size_group`: an integer representing the desired size of each group

It returns a tuple containing:
- a list of lists, where each inner list represents a group of players
- a list of players that were not included in any of the groups due to an uneven number of players

This function creates groups of players by sorting the `active_players` list by rank and then selecting players from each rank in turn to fill the groups. Any remaining players that do not fit evenly into the groups are added to the `other` list and returned along with the list of groups.

## `get_rank`

This function takes in one argument:
- `player`: a player object

It returns the player's rank as an integer. This function is used as a key for sorting the `active_players` list in the `randomize_by_rank` function.


To start the server and install the required dependencies, run the following commands:

```
pip install -r requirements.txt
export FLASK_APP=app.py
flask run
```

These commands will install the required dependencies, set the `FLASK_APP` environment variable to `app.py`, and start the server.

You can then access the endpoints at `http://localhost:5000`.
