# Social-Login-OAuth2-Security-Setup
Extra-detailed instructions are located here:
OAuth2 Setup Guide

OAuth2 Setup Information
To get started with Google OAuth2 in this project, follow these steps:

Google Cloud Console Setup:

Navigate to the Google Cloud Console.
Create a new project.
Set up OAuth consent screen (make sure to set the type as external).
Add test users (use Gmail accounts).
Create OAuth credentials (set application type as web application).
Copy your client ID and client secret to the appropriate fields in the application.properties file.
Configure application.properties:

spring.security.oauth2.client.registration.google.client-id=YOUR_GOOGLE_CLIENT_ID
spring.security.oauth2.client.registration.google.client-secret=YOUR_GOOGLE_CLIENT_SECRET
spring.security.oauth2.client.registration.google.redirect-uri=http://localhost:8080/login/oauth2/code/google
spring.security.oauth2.client.registration.google.scope=openid,profile,email
Run the application and navigate to /login to trigger the Google OAuth2 login flow.

For more in-depth instructions, you can check out Dan Vega's OAuth2 Video.

Testing Your Setup
Run the application.
Navigate to the Login Page: When you first access the application, go to http://localhost:8080/ or /home as your entry point.
To initiate the login flow, you may need to manually enter /login in the URL bar (e.g., http://localhost:8080/login).
Successful Login: After logging in, you should be redirected to /secured by default (or another page if customized).
