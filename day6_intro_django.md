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
    path('new', views.create),	   
]

```

## Views
Views in Django is our controller file. This is where our action methods will live.

soup/views.py

```py
from django.shortcuts import render

def index(request):
    # this is the way we can pass data from our server to our templates
    context = {
        "first_name": "Mr. Nibbles",
        "last_name" : "McNibs"
    }
    # We must not forget to include it in the render method.
    return render(request,'index.html',context)

def create(request):
    return render(request, 'new.html')
```

## Templates and Static Files

If we look at the example code above, we use context to pass data to our html files.  Context is the dictionary that you pass, and then you can access the data by the key names.<br>
<br>
We must also create a templates folder.<br>
<br>
File Structure with Templates:

```
├ soups_on/
    ├ soup/
        ├ templates/
            ├ index.html
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

index.html

```html

<h1>{{ first_name }} {{ last_name }}</h1>

```

For out static files like css, images, and javascript, we need to do some set up.<br>
<br>

Folder Structure with Static files:

```
├ soups_on/
    ├ soup/
        ├ templates/
            ├ index.html
        ├ static/
            ├ css/
                ├ style.css
            ├ img/
                ├ profile.png
            ├ js/
                ├ script.js
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

index.html

```html
<head>
    <meta charset="utf-8">
    <title>Index</title>
    {% load static %}
    <link rel="stylesheet" href="{% static 'css/style.css' %}">    
    <script src="{% static 'js/script.js' %}"></script>
</head>

```


##  POST ROUTES && FORM SUMBITION

Now we are going create a form so that the user of our website can send information to our server.<br>
To do this we need to use a POST request, and we need to be able to detect that in views.py file.<br>
<br>


This is how we set up the form on the html.

new.html

```html

<form action="/create" method="post">
    <!-- We need this csrf token to prevent hackers from submitting false data. -->
    <!-- It lets our server know that it is coming from our html page. -->
  {% csrf_token %}
  <label>First Name:</label>
  <!-- The name attribute on an input tag will correspond to the key of the post dictionary that we send to our server. -->
  <input name="first_name" type="text">
  <label>Last Name:</label>
  <input name="last_name" type="text">
  <input type="submit" value="Submit"  >
</form>

```


soup/views.py

```py
from django.shortcuts import render, redirect

def create(request):
    # This is how we detect a post request
    if request.method == "POST":
        # Now we pull that data from the post request dictionary!!!
        first_name = request.POST["first_name"]
        last_name = request.POST["last_name"]
        # Must always redirect on a post request!!!!
        redirect('/')
```