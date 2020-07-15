# Do You Copy? Backend

## Setup Instructions
- [Install Python](https://www.python.org/downloads/): Many machines will come with Python out of the box, but this project requires version 3.6 or higher. If you have homebrew, you can use the command `brew install python`.
- [Installing Packages](https://packaging.python.org/tutorials/installing-packages/)
- Install Django: `pip install pipenv`, `pipenv shell`
- [Install Djongo](https://nesdis.github.io/djongo/integrating-django-with-mongodb/) `pip install djongo`
- Install MongoDB: Homebrew doesn't support Mongo anymore so we can use [this](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/) instead.
- [Robo 3T](https://robomongo.org/)
- [MongoDB in Robo 3T](https://kb.objectrocket.com/mongo-db/how-to-setup-a-mongodb-database-in-robo-3t-344#:~:text=Creating%20the%20MongoDB%20Database%20in%20Robo%203T%20GUI,-Once%20the%20connection&text=To%20create%20a%20new%20MongoDB,the%20%E2%80%9CDatabase%20Name%E2%80%9D%20field.)

## Testing
Once everything is working we should be able to:
- Run mongod by using the command `brew services start mongodb-community@4.2`
- Create a DB in mongo by running `mongo` and then, inside the new shell, `use YOUR_CHOSEN_DB_NAME`
- Update the settings.py file to include your chosen db name (replcae YOUR_CHOSEN_DB_NAME with the name of your mongo db). It will look like this:
```
DATABASES = {
    'default': {
        'ENGINE': 'djongo',
        'NAME': 'YOUR_CHOSEN_DB_NAME',
    }
}
```
- Inside of our project in the command line, run the command `python manage.py migrate`
- Connect your DB to Robo 3T and view the newly created collections, most notably `games_game`