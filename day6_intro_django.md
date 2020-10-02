# Day 6 Intro to Django

<img src="https://github.com/adion81/python_lectures/blob/master/assets/django.png" alt="Python" width="400px" > 

## What is Django
Django is a framework for Python that super modularizes your application.  It use the MTV Design pattern.<br>
<br>

## MTV Design Pattern
MTV stands for Models - Templates - Views<br>
<br>

not<br>
<br>
<img src="https://github.com/adion81/python_lectures/blob/master/assets/mtv.jpg" alt="MTV" width="400px" > 

| MODELS                     |  TEMPLATES                 | VIEWS               |
|----------------------------|-------------------------------|-------------------------------|
| `We define our classes` | `HTML Files` | `Controller (Action) Methods / Routes`|


## The Setup

We must activate our Django Environment in order spin up a project. We are gonna create an application called Soups On<br>
<br>

`(djangoPy3Env) ~  django-admin startproject soups_on`<br>
<br>
This creates our project for django. We can create multiple apps on the project if we want.<br>
<br>
But even if we only want one project we must create a project like so.<br>
<br>
We need to navigate into our django project.

`(djangoPy3Env) cd soups_on `

Then we can create our app with this line.

`(djangoPy3Env) python manage.py startapp soup`


This is what our project folder will look like right out of the box.

```
├ soups_on/
    ├ soup/
        ├ migrations/
            ├ __init__.py
        ├ __init__.py
        ├ admin.py
        ├ apps.py
        ├ models.py
        ├ tests.py
        ├ admin.py
        ├ views.py
    ├ soups_on/
        ├ _pycache_/
        ├ __init__.py
        ├ settings.py
        ├ urls.py
        ├ wsgi.py
    ├ manage.py
```

This is alot coming right out of the box, but take note that there are project level files and app level files that we now need to manage.<br>
<br>
Also `manage.py` is our file that we run to start up our django project.<br>
<br>
`python manage.py`
<br>

We must now add a pointer in our `settings.py` to our app we just made.


soups_on/settings.py

```py
# Application definition

INSTALLED_APPS = [
    # This is the line that we add . . .
    'soup',
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
]
```

## Routing

We must now set up routing within our project level files.  Route requests coming from the client hit the project level urls.py first.<br>
<br>

soups_on/urls.py

```py
# remember to include the include here
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    # this is where we navigate our project to our soup app
    path('', include('soup.urls'))
]

```

We then need to create a `urls.py` within our soup app folder

soup/urls.py

```py

# We must import path here
from django.urls import path 

# We must import our views file from soup/views.py  
from . import views

# Now we can attach each route to the specified route in our views.py
urlpatterns = [
    path('', views.index),	   
]

```

## Views
Views in Django is our controller file. This is where our action methods will live.

soup/views.py

```py
from django.shortcuts import render

def index(request):
    return render(request,'index.html')

```

## Templates and Static Files

## POST Request && Submitting Forms