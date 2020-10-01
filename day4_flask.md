# Flask

<img src="https://github.com/adion81/python_lectures/blob/master/assets/flask.png" alt="Flask" width="200px" > 

<details>
    <summary>What is Flask?</summary>
    Flask is light weight framework that we can use to make web applications.
</details>

## Http Response / Request Cycle

<img src="https://vectr.com/adion81/c8R4t9Gpm.svg?width=500&height=280&select=c8R4t9Gpmpage0" alt="response request cycle" width="300px">
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
├ HelloWorld/
    ├ templates/
        ├ index.html
        ├ another.html
    ├ server.py
```


