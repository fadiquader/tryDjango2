# tryDjango2

## create blank project

```
mkdir projectName && cd projectName
```

```
virtualenv -p python3 env
```

activate on Mac/Linux

```
source bin/activate
```

```
pip install django // you can choose version django==2.0.5

```

```
mkdir src && cd src 
```

create djangp project

```
django-admin.py startproject projectName . 
```
create seetings directory
```
cd projectName
```

```
mkdir settings && cd settings
```
```
create __init__.py

// put inside

from .base import *

from .production import *

try:
   from .local import *
except:
   pass
```

Change BASE_DIR in settings.py:
```
BASE_DIR = os.path.dirname(os.path.dirname(os.path.abspath(__file__)))
// to
BASE_DIR = os.path.dirname(os.path.dirname(os.path.dirname(os.path.abspath(__file__))))
```
move settings.py to settings/base.py
```
copy base.py to local.py
```

Some other common installations (optional):
```
// for a postgresql database
pip install psycopg2

// for a mysql database
pip install mysqlclient #python3
pip install MySQL-python #python2

// for use on heroku
pip install gunicorn dj-database-url

pip install django-crispy-forms
pip install pillow
```

inside src directory
Create requirements.txt file
```
pip freeze > requirements.txt
```
if you have project with requirements.txt, you can install dependencies
```
pip3 install -r requirements.txt
```

Run Migration & Createsuperuser
```
python manage.py migrate
python manage.py createsuperuser
```
create bin/run.sh
```
sudo chmod +x run.sh
```
```
source env/bin/activate
cd src
python manage.py runserver
``