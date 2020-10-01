# Flask

<img src="https://github.com/adion81/python_lectures/blob/master/assets/flask.png" alt="Flask" width="200px" > 

<details>
    <summary>What is Flask?</summary>
    Flask is light weight framework that we can use to make web applications.
</details>

## Http Response / Request Cycle

<img src="https://vectr.com/adion81/c8R4t9Gpm.svg?width=500&height=280&select=c8R4t9Gpmpage0" alt="response request cycle" width="500px">
<details>
    <summary>5 Common HTTP Verbs</summary>
    <ul>
        <li>GET</li>
        <li>POST</li>
        <li>PUT</li>
        <li>PATCH</li>
        <li>DELETE</li>
    </ul>
</details>


## Setting Up Flask
In order to use Flask, we must set it up in our virtual environment.<br>
<br>

`cd my_environments`<br>
<br>
For Mac:

`source py3Env/bin/activate`<br>
<br>

For Windows(Command Prompt):

`call py3Env/Scripts/activate`<br>
<br>

server.py
```py

# This line imports the micro-framework
from flask import Flask

# This creates a instance of the flask class
app = Flask(__name__)

# Meow we can writes routes in our file!!!
# This is our index route
@app.route('/')
def index():
    return "Hello World"

@app.route('/another_route')
def another_route():
    return "Now we are masters of the interweb!!!"

# this is to enable debugging for our development.
if __name__=="__main__":
    app.run(debug=True)

```

## Rendering Templates(HTML)

We can even render templates from our flask server, but first there is some setup.<br>
<br>
The Folder structure:

```
├ hello_world/
    ├ templates/
        ├ index.html
        ├ another.html
    ├ server.py
```

Now in our server file we can import `render_template`.


server.py
```py

# We add render_template to this line!!!!
from flask import Flask, render_template

app = Flask(__name__)

@app.route('/')
def index():
    # instead of returning a string we now return render a template or html file.
    return render("index.html")

@app.route('/another_route')
def another_route():
    # We can even pass data from our server to our html page.
    return render("another.html",message="Robots arise!!!")

if __name__=="__main__":
    app.run(debug=True)

```

**Take note that what you call your variables in your render method, you must call it in the html file.**

another.html
```html
<!-- This weird syntax is Jinja2 and it allows us to insert data from our server -->
<h1>{{ message }}</h1>
```

## Static Files

We can now start adding in our css, img, and other static files.

Our Folder Structure:

```
├ hello_world/
    ├ templates/
        ├ index.html
        ├ another.html
    ├ static/
        ├ stylesheets/
            ├ style.css
        ├ img/
            ├ img.png
        ├ js/
            ├ script.js
    ├ server.py
```


index.html

```html
<html>
<head>
    <link rel="stylesheet" type="text/css" href="{{ url_for('static', filename='css/my_style.css') }}">
    <!-- linking a javascript file -->
    <script type="text/javascript" src="{{ url_for('static', filename='js/script.js') }}"></script>
    <!-- linking an image -->
    <img src="{{ url_for('static', filename='img/img.png') }}">
</head>
</html>
```

**AND NOW WE HAVE A WEB SERVER!!!**

