1. asp.net webapi project (.net 4.5.2)

2. Install-Package System.IdentityModel.Tokens.Jwt -Version 5.1.4

3. Verifying The jwt web api  :
5. we will need to add a  class at root level that extends from DelegatingHandler  and we will override SendAsync  method. Please note purpose of adding this class is to intercept incoming HTTP Request and Retrieve and Validate Token.

Untill this point if you don’t know what is purpose of DelegatingHandler is Please read this post before moving forward. HTTP Message Handler in Web API

I will name this class TokenValidationHandler 

Generating the JWT Web Api:
register Message Handler class in webapiconfig.cs


https://github.com/seanonline/Webapi_JWT_Authentication

http://www.decatechlabs.com/secure-webapi-using-jwt

post request:

http://localhost:50353/api/Login

headers: Content-Type: application/json

body:
{
	"Username":"vaishali",
	"Password":"admin"
}


body:

GET request http://localhost:50353/api/Values

headers: Content-Type: application/json,
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1bmlxdWVfbmFtZSI6InZhaXNoYWxpIiwibmJmIjoxNTIxMDU3NTMxLCJleHAiOjE1MjE2NjIzMzEsImlhdCI6MTUyMTA1NzUzMSwiaXNzIjoiaHR0cDovL2xvY2FsaG9zdDo1MDM1MyIsImF1ZCI6Imh0dHA6Ly9sb2NhbGhvc3Q6NTAzNTMifQ.tQYTVjwZ2CH-QaOyFM4BEB3m1YN6ov5y47vim_V3dpk


output: 
[
    "value1",
    "value2"
]