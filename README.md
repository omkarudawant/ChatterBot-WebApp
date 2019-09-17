# ChatterBot-WebApp

Ensure that all the requirements are installed. (run `pip install -r requirements.txt`).

## How to Run ?

In terminal,
 
 `python app.py`.

## Instructions for Heroku

If you are deploying on Heroku, you will have to change the database adapter from `chatterbot.storage.SQLStorageAdapter` to `chatterbot.storage.MongoDatabaseAdapter` since SQLite3 isn't supported. 

To do this simply change the following line:

`english_bot = ChatBot("English Bot", storage_adapter="chatterbot.storage.SQLStorageAdapter")`

To 

```
english_bot = ChatBot("English Bot", 
                     storage_adapter = "chatterbot.storage.MongoDatabaseAdapter",
                     database = mongodb_name,
                     database_uri = mongodb_uri)
```

where `mongodb_name` is the name of the database you wish to connect to and `mongodb_uri` is the URI of a remote instance of MongoDB.
