In order to run the microservice, you must have Rabbit MQ installed and a working knowledge of remote procedure calls. Link to rabbit MQ tutorial: https://www.rabbitmq.com/tutorials/tutorial-six-python.html
This microservice also assumes you have a MongoDB cluster set up as the saving and loading of game data will happen via the database.

First in order to interact with the microservice, you need to run the microservice_server.py file, which can be done in the command line as such
``` python microservice_server.py```
Then run the microservice_client.py file with 
``` python microservice_client.py```

It will ask if you would like to load or save game data. To save game data, type in 'save' then it will receive the game data as a JSON string. There is an example in the file:
```
    game_data = {
        "_id": 678,
        "saveSlot": 1,
        "petName": "Woofie",
        "health": 10,
        "hunger": 15,
        "thirst": 20,
        "hygiene": 25
    }
```
It will then insert the game data by id into Mongo DB (or if you don't have an id, it will auto generate one for you). After saving, there will be a confirmation showing that it was successful.

To load a saved state, you need the game id, which you input into the client after requesting that you want to load data. The client will take the game_id and search the database for the previously saved information and display it back to you as a JSON string if it successfully found the information.
