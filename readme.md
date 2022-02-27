# Megapilos

This project is to explore creating a single API for multiple databases.  It is patterned after [this description](https://www.attilatoth.dev/posts/flask-sqlalchemy-multiple-dbs/#:~:text=Configure%20Flask-SQLAlchemy%20to%20use%20multiple%20databases%201%20Configure,separate%20config%20file.%20...%205%20Wrapping%20up.%20).

&nbsp;&nbsp;

# Project Contents

This is the standard ApiLogicProject, with the following changes (I've tried to denote this with *megapilos*):
* `config.py` is altered to include the `cls` bind
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

But, `get` fails since the ***database is not opened:***

```
safrs.errors.GenericError
Generic Error: (sqlite3.OperationalError) no such table: offices
[SQL: SELECT offices."officeCode" AS "offices_officeCode", offices.city AS offices_city, offices.phone AS offices_phone, offices."addressLine1" AS "offices_addressLine1", offices."addressLine2" AS "offices_addressLine2", offices.state AS offices_state, offices.country AS offices_country, offices."postalCode" AS "offices_postalCode", offices.territory AS offices_territory 
FROM offices ORDER BY offices."officeCode", offices.city, offices.phone, offices."addressLine1", offices."addressLine2", offices.state, offices.country, offices."postalCode", offices.territory, offices."officeCode"
 LIMIT ? OFFSET ?]
[parameters: (10, 0)]
```

![Get Failes](/images/db-not-open.png?raw=true "Optional Title")
