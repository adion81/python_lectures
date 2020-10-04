# Day 7 - Session
<img src="https://github.com/adion81/python_lectures/blob/master/assets/django.png" alt="Python" width="400px" > 

## What is Session

Session is a cookie that lives on your browser and allows the website to recognize that a user is signed in.<br>
<br>
It's also a dictionary and unsecure.  So no sensitive data should ever be put into it.

## The Setup

The first thing we need to do to setup session in Django is to migrate our migrations . . .<br>
<br>
This is how that session cookie gets set up.

`python manage.py migrate`

And now we have access to that dictionary with in our views.py!!!!

## Using Session

soup/views.py

```py

def index(request):
    # We can detect if the key - value pair is in the session dictionary
    if "user_name" in request.session:
        # If the name is in session we can just go to the page.
        return render('index.html')
    else:
        # If not then we can set it and render the html.
        request.session['user_name'] = "Benny Bob"
        return render('index.html')

```
Now we can access it within our template!!!

index.html

```html
<!-- This is how we can call it in our templates -->
<h1>{{ request.session.user_name }}</h1>

```

***And now we are cookie people!!!***

<img src="https://github.com/adion81/python_lectures/blob/master/assets/cookie.gif" alt="Cookie!!!" width="500px" > 