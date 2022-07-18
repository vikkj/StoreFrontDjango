# Simple Website using Django and database sqlite3

## Python modules required:
1. Django Admin

## How to work with django
Refer this : [Django Documentation](https://docs.djangoproject.com/en/4.0/)

## How to work inside data base
Refer this : [flask_sqlalchemy Documentation](https://flask-sqlalchemy.palletsprojects.com/en/2.x/)

## SQLite3 Commands can be found in this page
Refer this : [SQLite3](https://docs.python.org/3/library/sqlite3.html)

## How the database model is registered in the main project (in this case about storefront)
1. Create a app using command : ```python manage.py startapp home```
2. In home.models.py file create the database model you want to create (in this case 'class Contact')
3. Register you database models inside home.admin.py by importing home and ```admin.site.register(Contact)```
4. Register your app on main project by adding the name of the project inside the storefront.settings.py under INSTALLED_APPS
5. In terminal run this command : ```python manage.py makemigrations```
6. Followed by : ```python manage.py migrate```
7. And Ta Da!!! Your newer database has been created.

## How  to log in the django managed sqlite3 database
1. In the terminal run this : ```python manage.py shell```
2. The above command will put you into a interactive shell where you can work with database and can work with python programs as well. Below is already listed CRUD Operations that can be performed using this terminal

## Simple Crud operations on sqlite3
1. Creating new entry in database : ``` user_1 = User(
    username=request.form['name'],
email=request.form['email'],
gender=request.form['gender'],
skill=request.form['skill'],
certification=request.form['cert'],
phoneno=request.form['ph'],
address=request.form['add'],
education=request.form['edu'],
profile_img=request.files['file'],
specialization=request.form['special'] ```
2. Adding the above created to the current db session: ``` db.session.add(user_1) ```
3. Commiting the above change: ``` db.session.commit() ```
4. Dropping all the models created in the db: ``` db.drop_all() ```
5. Deleting a single entry in the database: ``` 
db.session.delete(User.query.filter_by(username=='<something>').first())
db.session.commit() ```

Note: To run all the above commands in cmd you have to first open cmd in current directory where you have this python file. Then under python interpreter type this command: ``` from Controller import db,User,RegisteredUsers ``` then you can use database from interpreter