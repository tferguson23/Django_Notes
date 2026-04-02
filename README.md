# Django Notes

## What is Django: Introduction to Backend Frameworks
Django is a high-level (focus on business logic and core functionality) Python web framework that enables developers to build robust, scalable, and secure web applications quickly. It emphasizes rapid development, clean and pragmatic design, and comes with many built-in tools that eliminate the need to reinvent the wheel. 

Every Django app follows MVT architecture. The importance of a clean design is that it creates an ogranized atmosphere and is easier to maintain. 

+ Authentication
+ URL routing: URL is mapped to a specific view. 
+ Forms & Validation
+ Database migrations: any changes to the structure will be automatically updated. 

## How web applications work:
The user interacts with the client/browser, which then interacts with the server. The server will sned the appropriate request response (sending data back). 

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
1. Identify your path.\
   cd: changes working directory of the working drive or lettered drive. Type username to get into username folder. 
   dir: identifying all files present in the C drive. \
2. Install virtual envrionment
   ```
   pip install virtualenv
   cd pro #this creates a folder for the envrionment to go.
   C:\Users\theresaferguson\pro>virtualenv #virtualenv will be installed in pro folder. 

    ```
3. Activate virtual envrionment


## Glossary 
**Robust Apps:** Apps which do not crash, manages errors gracefully.\
**Scalable Apps:** Apps that handle high traffic websites without affecting performance. \
**Secure Apps:** Provides protection against common vulnerabilities such as SQL injection, Cross-Site Scripting(XSS), Cross-Site Request Forgery(CSRF) & Clickjacking. \
**Model-View-Template (MVT):** architecute that promotes clean and pragmatic design. \
**Virtual Envrionment:** Each particular project in Django is installed in an isolated envrionment so that neither project will affect another. 
