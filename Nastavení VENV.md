Vytvoření virtuálního prostředí.

```console
$ mkdir myproject
$ cd myproject
$ python3 -m venv venv
```

or on Windows
```console
venv\Scripts\activate
```

Install Flask
```console
$ pip install Flask
$ pip install Flask-SQLAlchemy
```

Set environment variables in terminal

or on Windows
```console
$ set FLASK_APP=app.py
$ set FLASK_ENV=development
```

Run the app
```console
$ flask run
```