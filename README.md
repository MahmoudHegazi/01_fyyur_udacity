# 01_fyyur_udacity


    
# how to start it

1.  ```cd project folder```
2.  ```python -m virtualenv env```
3.  ```#not used python -m venv env ``` 
4.  ```source env/Scripts/activate```
5.  ```export FLASK_APP=app```
6.  ```flask run```
7.  ```connect to postgres from CMD or GitBash psql -U postgres ```
8.  ``` create Database with name fyyur and db user with previelegs with name purple_fish and password 123```
9.  ``` psql -h localhost -d fyyur -U purple_fish to connect #db connect ```
10. ```visit 127.0.0.1:5000```

# Database Info

1. Table show ( relationship with Artist and Veneue )
2. Table Artist
3. Table Veneue
4. db user pruple_fish, db name fyyur


# app features:
1- Add, Read, Delete, Update To (Venues, Shows, Artist)
2- Search function case-insensitive.
3- bootstrap


# languages used:
Python, HTML5, ES6




# usefull links

1. https://realpython.com/flask-by-example-part-1-project-setup/
2. https://stackoverflow.com/questions/9794413/failed-to-push-some-refs-to-githeroku-com
3. https://wtforms.readthedocs.io/en/2.3.x/fields/ (fileds and inputs)


# udacity rubric features

1. There are no build or compilation errors in running code and launching the web app.
2. A user can successfully execute a Search that queries the database.
3. A user can view a Venue Page with venue and artist information from the database.
4. A user can view an Artist Page with venue and artist information from the database.
5. A user can create new venue listing via the New Venue Page.
6. A user cannot submit an invalid form submission (e.g. using an invalid State enum, or with required fields missing; missing city, missing name, or missing genre is not required).
7. A user can create new artist listings via the New Artist Page.
8. A user cannot submit an invalid form submission (e.g. without required fields)
9. A user can search for an artist from the venue page, and choose them for a show, specifying a date-time.

# create db and Notes

1.  db from CMD 
2.  in CMD psql -U postgres
3.  ```psql -h localhost -d fyyur -U purple_fish  to connect```
4.  add path https://sqlbackupandftp.com/blog/setting-windows-path-for-postgres-tools
5.  important https://stackoverflow.com/questions/24341767/execution-of-postgresql-by-a-user-with-administrative-permissions-is-not-permitt
6.  ```net user postgres your_password /add``` then ```runas /user:postgres cmd.exe```
7. https://sqlbackupandftp.com/blog/setting-windows-path-for-postgres-tools
8. you have to putt the app.config in the app file and connection link to db  this is what you need db user : purple_fish, password: 123, db_name=fyyur

```
app.config['SQLALCHEMY_DATABASE_URI'] = 'postgresql://purple_fish:123@localhost:5432/fyyur'
app.config['SQLALCHEMY_TRACK_MODIFICATIONS'] = False
#this to show arabic address 
app.config['JSON_AS_ASCII'] = False
app.config["IMAGE_UPLOADS"] = 'uploads'
db = SQLAlchemy(app)
```

9. you need for db troubleshoot: https://stackoverflow.com/questions/20744277/sqlalchemy-create-all-does-not-create-tables
10. ```db.create_all()``` will create and wait commit command ```db.session.commit()```
11.  you can open external CMD for database
12. if not show ID in Cretae new show page just refresh the flask app
