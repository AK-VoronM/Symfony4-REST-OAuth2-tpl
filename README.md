# SymfonyRESTOAuth2_tpl
Require: PHP 7.1
Bundles:
 friendsofsymfony/rest-bundle
 sensio/framework-extra-bundle
 jms/serializer-bundle
 symfony/validator
 symfony/form
 symfony/orm-pack
 friendsofsymfony/user-bundle
 friendsofsymfony/oauth-server-bundle

We use a basic Symfony skeleton project that is recommended for more barebones applications like microservices and APIs. Symfony 4.x has a new and more simplified directory structure. 

Routes:
 POST /createClient 
  {
    "redirect-url": "some.url",
    "grant-type": "password"
  }
 Response:
  {
    "client_id": "some string",
    "client_secret": "enother string"
  }
  
  POST /oauth/v2/token
   {
    "client_id": "some string",
    "client_secret": "enother string",
    "grant_type": "password",
    "username": "login",
    "password": "password"
  }
 Response:
  {
    "access_token": "Access token string",
    "expires_in": 86400,
    "token_type": "bearer",
    "scope": null,
    "refresh_token": "refresh token string"
  }
 POST /oauth/v2/token
  {
    "client_id": "some string",
    "client_secret": "enother string",
    "grant_type": "refresh_token",
    "refresh_token": "refresh token string"
  }
 Response:
  {
    "access_token": "New access token string",
    "expires_in": 86400,
    "token_type": "bearer",
    "scope": null,
    "refresh_token": "New refresh token string"
  }
