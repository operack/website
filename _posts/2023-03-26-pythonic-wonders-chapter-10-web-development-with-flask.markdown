---
title: "Pythonic Wonders: Chapter 10 - Web Development with Flask"
author: mdomocos
date: 2023-03-26 09:10:00 +0200
categories: [Courses, Python]
tags: [operack, python, course]
math: false
mermaid: false
---
### Intro

Flask is a popular Python web framework used for building web applications. It is a lightweight framework that provides a simple way to create web applications.

#### Introduction to web development

Web development is the process of creating websites and web applications that can be accessed through the internet. Web applications are programs that run on web servers and can be accessed by clients through a web browser.

#### Setting up Flask

To use Flask, you need to install it using pip, a Python package manager. You can install Flask by running the following command in your terminal:

```shell
pip install flask
```

#### Routing and handling requests

Routing is the process of mapping URLs to view functions. View functions are Python functions that return a response to a client's request. Flask uses the `route` decorator to map URLs to view functions. For example:

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'Hello, World!'
```

This code defines a view function that returns the string `'Hello, World!'` when the root URL is requested (`'/'`).

#### Templating with Jinja2

Jinja2 is a powerful and flexible template engine for Python. It allows you to create templates that can be filled with data dynamically. Flask uses Jinja2 as its default template engine.

Here's an example of using Jinja2 to render a template with data:

```python
from flask import Flask, render_template

app = Flask(__name__)

@app.route('/hello/<name>')
def hello(name):
    return render_template('hello.html', name=name)
```

In this code, the view function takes a name parameter from the URL and passes it to the `render_template` function along with the name of the template to render (`'hello.html'`). The `hello.html` template might look something like this:

```html
{% raw %}
<!doctype html>
<html>
  <head>
    <title>Hello</title>
  </head>
  <body>
    <h1>Hello, {{name}}!</h1>
  </body>
</html>
{% endraw %}
```

This template uses Jinja2's syntax to render the `name` variable passed in by the view function. When the template is rendered, the resulting HTML will contain the string "Hello, " followed by the value of the `name` parameter.

#### Running the Flask application
To run the Flask application, save the code for the app in a file called app.py. Then, open a terminal or command prompt and navigate to the directory containing app.py. Finally, run the following command:

```shell
python app.py
```

This command will start the Flask development server, which will listen for requests on your computer's localhost address (usually [http://127.0.0.1:5000/](http://127.0.0.1:5000/)). You can access the app in your web browser by visiting this address.

That's it! You should now have a working Flask application that you can customize and build upon to create your own web applications.
