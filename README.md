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

### Keywords 
**def** defines the function; accompanied by the chosen view name. 
   **return** required for def. 
**import** 



## Glossary 
**Robust Apps:** Apps which do not crash, manages errors gracefully.\
**Scalable Apps:** Apps that handle high traffic websites without affecting performance. \
**Secure Apps:** Provides protection against common vulnerabilities such as SQL injection, Cross-Site Scripting(XSS), Cross-Site Request Forgery(CSRF) & Clickjacking. \
**Model-View-Template (MVT):** architecute that promotes clean and pragmatic design. \
**Virtual Envrionment:** Each particular project in Django is installed in an isolated envrionment so that neither project will affect another. You can create as many environments as you want. 
**class:** a datatype, object constructor. 
**parameter:** a variable name listed inside the parenthesis of a function definition. 