# Megapilos

This project is to explore creating a single API for multiple databases.  It is patterned after [this description](https://www.attilatoth.dev/posts/flask-sqlalchemy-multiple-dbs/#:~:text=Configure%20Flask-SQLAlchemy%20to%20use%20multiple%20databases%201%20Configure,separate%20config%20file.%20...%205%20Wrapping%20up.%20).

&nbsp;&nbsp;

# Project Contents

This is the standard ApiLogicProject, with the following changes (I've tried to denote this with *megapilos*):
* `config.py` is altered to include some binds
* `database/models_cls.py` has been added (models for the `cls` bind)
* `api/expose_api_models.py` to expose `models_cls.py`

&nbsp;&nbsp;

# Setup

The usual:
```
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

This should enable you to run launch configuration `ApiLogicServer`.

&nbsp;&nbsp;

# Status

The API starts, and the swagger runs, exposing the `office` endpoint.

But, `get' fails since the database is not opened:

![Get Failes](/images/db-not-open.png?raw=true "Optional Title")
