# Django Notes

## What is Django: Introduction to Backend Frameworks
Django is a high-level (focus on business logic and core functionality) Python web framework that enables developers to build robust, scalable, and secure web applications quickly. It emphasizes rapid development, clean and pragmatic design, and comes with many built-in tools that eliminate the need to reinvent the wheel. 

Every Django app follows MVT architecture. The importance of a clean design is that it creates an ogranized atmosphere and is easier to maintain. 

+ Authentication
+ URL routing: URL is mapped to a specific view. 
+ Forms & Validation
+ Database migrations: any changes to the structure will be automatically updated. 

## How web applications work:
The user interacts with the client/browser, which then interacts with the server. The server will send the appropriate request response (sending data back). 

## Programming servers: Easy as pizza !
+ Handling incoming requests
+ Building routing logic
+ Integrating databases
+ Session management
+ Handling authentication 
+ Security 

### Making use of 'pre-made' ingredients:
We can use backend frameworks for our project requirements. 
+ Python: Django, Flask, Fast API
+ Java: Spring Boot
+ JavaScript: Express.js
+ PHP: Laravel, Symfony
+ Ruby: Ruby on Rails
+ C#: ASP.NET Core
+ GO: GIN, Echo
+ Rust: Actix-web, Rocket

## I. Creating a Virtual Envrionment
1. Create a new folder.\
   cd: changes working directory of the working drive or lettered drive. Type username to get into username folder.\ 
   ls: lists out all available files present in the directory.
2. Install virtual envrionment
   ```
   open terminal
   cd desktop
   cd pro #this creates a folder for the envrionment to go.
   pip3 install virtualenv
   virtualenv env #creates an envrionment named env
    ```
3. Activate virtual envrionment
   ```
   cd env
   source bin/activate #program that activates the envrionment 
   ```

## II. Install Django 
```
(env) C:\Users\theresaferguson\pro>pip install django
```

## III. Creating our Django project
+ Make sure you have your command prompt opened up
+ Make sure you have your virtual envrionment activated
+ Ensure you are in the project's folder
```
$ django-admin startproject mysite #creates django project
```
+ open mysite directory
  + within the project directory 'external/ROOT directory', we have an internal 
  + manage.py \
What the file does: 
```
python manage.py runserver #localhost development server
python manage.py makemigrations
python manage.py createsuperuser
```
### File purposes in the Root Directory:
**__init__.py:** marks current directory as a python package.\
**settings.py:** contains all settings for the Django project.\
**wsgi.py:** "web server gateway interface"; acts as an entry point for deploying our application.\
**asgi.py:** asyncronous gateway interface; used for handling asyncronous web protocols.\
**urls.py:** contains all url patterns that are required inside our application. Patterns used to match incoming client requests. 

## IV. Creating a Django App
### What is an app in Django: 
+ Can be split into multiple parts to maintain the project easily.
+ Apps together form the Django project.
> [!NOTE]
> Make sure you are inside the Root Directory.
```
$ cd desktop
$ cd pro
$ cd env
$ source bin/activate
$ cd mysite
$ python manage.py startapp myapp
```
## V. Myapp directory and the view file
The view file processes the url request. 
+ define a function that will act as a view. 
+ We are _returning_ a request such as the HttpResponse. 
+ Import a response class for the return response object. 

```
from django.http import HttpResponse  

def index(request): #request is the parameter
   return HttpResponse("Hello World")
``` 
### Connecting a view to a URL pattern
Each app should have its own url file. 

### How Django URL patterns work internally 
When a Django application receives a particular request, it will look at the variable in the settings.py file "ROOT_URLCONF" which points to a particular file. This will pair with any patterns that match the particular file. It will then call the view associated with that pattern. \
Look at video #18 for reminders on this connection. 

### Keywords and Functions
**def** defines the function; accompanied by the chosen view name.\
   **return** required for def. \
**import** \
**include** a function that includes a file in a path

## VI. Database Models 
+ Data in a database is stored in the form of tables. 
+ We use **models** to save data in an application. 
  + a blueprint used to create database table
  + a Python class
  + defined in models.py file

python manage.py migrate: a command that creates a database for the DATABASE APPS directly. \

You must makemigrations whenever you make changes to your models.
```
python manage.py makemigrations
python manage.py migrate
```
### Storing Data in a Database
ORM and how it works: whenever you want to save something, you need to create and object which can be updated or deleted. Objects require a class. 

### Saving data with the API 
```
python manage.py shell
```
+ Create a python object and object.save()
Add a string representation of the particular model: 
```
   def __str__(self):
      return self.item_name()
```

## VII. Admin Panel 
**Connecting admin to the models:**
In your admin.py folder:
```
from .models import Items

admin.site.register(Items)
```

### Retireving Objects
Model + Manager + Method: Item.objects.all()

## VIII. Templates 
Allow us to combine the dynamic and static components into one and render them together. (using the render method)
```
return render(request,"myapp/index.html")  #you are rendering the template from the templates myapp index.html folder and file. 
```
Providing _context_ to templates: whenever you are rendering a template, you can add context (data). 
+ You can make use of key:value pair as a context object. 
+ In a template.html, you need to distinguish that something is a variable with double curly braces. {{}}
  + The query set will be returned when the variable is distinguished because it is rendering <mark>Item.objects.all()</mark>

### Template formatting
**Creating a for loop in templates** \
This will allow the template to read the actual items in item_list as their variable names instead of the queryset format. 
```
{% for item in item_list %}
    {{ item }}
{% endfor %}
```
**Tags** these can be used in for loops. 
+ **<ul>** unordered list
+ **<li>** list tag
+ **<br>** gives a line break
+ **<a href="">** makes the text a hyperlink

## VIIII. Creating a detailed view template
+ Add another view in views.py file Dwith def and return. 
+ Use an f string and curly braces. 
+ Create url pattern for new view.
+ Link specifc id items using: 
  ```
   <a href="/myapp/{{item.id}}">
        {{ item.item_name }} ---- {{ item.item_price }} ---- {{ item.item_description }}    
        </a>
   ```
**Django Template Language** 
How we render the template language with DTL syntax. 
+ Templating Engine: Jinja2
+ {{}}: defines a variable; access or define any veriables that you may have. 
+ tags: allow of to define different things.

**How to remove hardcoded urls and the alternative:**
Hardcoded urls: contains a static and dynamic part. Not ideal for needing to change the urls frequently \
Dynamic urls: assign names to the path in urls.py and change the url in index.html by uting a tag:
```
<a href="{% url 'detail' item.id %}">
```
**Namespacing, avoiding name conflicts**\
+ Go to urls.py inside of your _application_
+ Type app_name='myapp'
+ This requires you to update the template url: <a href="{% url 'myapp:detail' item.id %}"> 

## X. Styling our application and static files _static/myapp_


## Glossary 
**Robust Apps:** Apps which do not crash, manages errors gracefully.\
**Scalable Apps:** Apps that handle high traffic websites without affecting performance. \
**Secure Apps:** Provides protection against common vulnerabilities such as SQL injection, Cross-Site Scripting(XSS), Cross-Site Request Forgery(CSRF) & Clickjacking. \
**Model-View-Template (MVT):** architecute that promotes clean and pragmatic design. \
**Virtual Envrionment:** Each particular project in Django is installed in an isolated envrionment so that neither project will affect another. You can create as many environments as you want. \
**Application v Project folders:** 
**views:** Functions that handle incoming URL request and send back HTTPResponse.\
**class:** a datatype, object constructor. \
**parameter:** a variable name listed inside the parenthesis of a function definition. \
**.** current directory\
**database:** an organized collection of data stored electronically. \
**Object Relational Mapper(ORM):** Elimantes the need of SQL to create databases through Django. \
**Models:** Allow us to create database tables without having to write SQL. \
**Field:** a place where you can store information, a form where you can enter data. \
**Dunder:** double underscore string representation.\
**self:** how we identify the particular instance. 
**Django template language:** using tags and variables
