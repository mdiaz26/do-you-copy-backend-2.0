# Do You Copy? Backend

## Setup Instructions
- [Install Python](https://www.python.org/downloads/): Django requires Python version 3.6 or higher. Check version with `python -V`. If it does not meet the Django requirement, follow the instructions in the provided link. If you have homebrew, you can use the command `brew install python`. [This link](https://dev.to/malwarebo/how-to-set-python3-as-a-default-python-version-on-mac-4jjf) also provides useful tips for switching Python versions.
- Install Django: Now that your Python is up to date, you should be able to install Django. We ideally install Django in a virtual environment inside of our project, so, from within the project's directory, run `pip install pipenv`, `pipenv shell`, and finally `pipenv install django`
- [Install Djongo](https://nesdis.github.io/djongo/integrating-django-with-mongodb/): Djongo helps connect Django with MongoDB. Run the command `pip install djongo`.
- Install MongoDB: Homebrew doesn't support Mongo anymore so we can use [these instructions](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/) instead.

## Additional Options:
- [Robo 3T](https://robomongo.org/): This program isn't necessary if you're already comfortable with MongoDB. If this is your first time using it, Robo 3T will make interacting with your data much easier. [This article](https://kb.objectrocket.com/mongo-db/how-to-setup-a-mongodb-database-in-robo-3t-344#:~:text=Creating%20the%20MongoDB%20Database%20in%20Robo%203T%20GUI,-Once%20the%20connection&text=To%20create%20a%20new%20MongoDB,the%20%E2%80%9CDatabase%20Name%E2%80%9D%20field) explains how MongoDB works with Robo 3T.

## Testing
Once everything is working we should be able to:
- Run mongod by using the command `brew services start mongodb-community@4.2`.
- Create a DB in mongo by running `mongo` and then, inside the new shell, `use YOUR_CHOSEN_DB_NAME`.
- Update the settings.py file to include your chosen db name (replcae YOUR_CHOSEN_DB_NAME with the name of your mongo db). It will look like this:
```
DATABASES = {
    'default': {
        'ENGINE': 'djongo',
        'NAME': 'YOUR_CHOSEN_DB_NAME',
    }
}
```
- Inside of the upper-most `do_you_copy` directory, run the command `python manage.py migrate` in the command line.
- Connect your DB to Robo 3T and view the newly created collections, most notably `games_game`.