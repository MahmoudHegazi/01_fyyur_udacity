# 01_fyyur_udacity


# usefull links

1. https://realpython.com/flask-by-example-part-1-project-setup/
2. https://stackoverflow.com/questions/9794413/failed-to-push-some-refs-to-githeroku-com
3. https://wtforms.readthedocs.io/en/2.3.x/fields/ (fileds and inputs)


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


# Join Notes and backref:
    ```shows = db.relationship('Artist', secondary=show, backref=db.backref('venue', lazy=True))```
    1. artist here not mean relation bettwen the Artist for each venue
    2. it define which table to join the join statment 3 tables should be givin in this case
    3. if there are a relation bettween the Venue and artist like store and item no need to define
    4. shows var in Artist but here we have diffrent 2 tables each one should give show backref
    
# how to start it

1.  ```cd project folder```
2.  ``` python -m venv env ``` 
3.  ```source env/Scripts/activate```
4.  ```export FLASK_APP=myapp```


