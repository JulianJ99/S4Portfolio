# Research – Identity providers

## Method
For this research, I'll be using the dot framework; more specifically, Library Research and Literature Study. 

To properly discover how best to set up an identity provider, I'll be checking out sources explaining more about how they work. I feel like this is the best way to discover which identity provider is right for my project.

## Problem definition

Programming projects often need an identity provider; and it is of utmost importance to make sure this is set up well, for the sake of user safety. Therefore, I&#39;m interested in researching what would be the best way to set up an Identity Service for my current project.

# Main question: How do you set up an Identity Provider?

## Sub questions

### What is an Identity Provider?

An identity provider is a system component that provides an end user or internet-connected device with a single set of login credentials that ensures the entity is who or what it says it is across multiple platforms, applications and networks.
For example, when a third-party website prompts end users to log in with their Google Account, Google Sign-In is the identity provider.

Lutkevich, B. (2021, September 28). identity provider. SearchSecurity. Retrieved June 21, 2022, from https://www.techtarget.com/searchsecurity/definition/identity-provider

### What are the advantages of an Identity Provider?

Identity Providers are easy to implement and can be used to solve multiple IT-problems, for example:
- Password fatigue; it lowers memory burden for your staff by being able to be used as a central login for all necessary logins at work
- Sprawling user lists; you won't need to make custom logins for all staff members because an Identity Provider eliminates that work for you
- Enhanced efficiency; If staff members need to access servers from a variety of devices, locations, and time zones then it's hard to manage access to all that without advanced server access management. An Identity Provider manages those details efficiently, so staff can focus on the other critical parts of their work.

Identity Providers (IdPs): What They Are and Why You Need One | Okta. Okta, Inc. Retrieved June 21, 2022, from https://www.okta.com/uk/identity-101/why-your-company-needs-an-identity-provider/

### What are some popular example of Identity Providers?
Some of the more well-known examples of Identity Providers are Microsoft, Google, Facebook and Github - these are all Identity Providers people have likely made use of, meaning it'll be reliable to assume your users will have an account on atleast one of these services.
Some examples are github, google, facebook and microsoft are some of the most popular providers which most people probably will have an account on at least one of these services

Lutkevich, B. (2021, September 28). identity provider. SearchSecurity. Retrieved June 21, 2022, from https://www.techtarget.com/searchsecurity/definition/identity-provider

### What is OAuth 2.0?

OAuth 2.0 is an example of an identity provider; it stands for "Open Authorization" and it's a standard designed to allow websites or applications to access resources hosted by other web apps on behalf of it's user; like allowing it's user to log in on their Google account, and then using the credentials from that Google account to log in as a verified user. 

It replaced OAuth 1.0 in 2012 and is now the industry standard for online authorization.

### How does oAuth2 work
OAuth 2.0 must acquire it's own credentials, a client id and client secret from the Authorization Server in order to identify and authenticate itself when requesting an Access Token.

The token request, exchange and response follow this general flow:

1. The Client requests authorization from the Authorization server, supplying the client id and secret to as identification; it also provides the scopes and an endpoint URI to send the Access Token or the Authorization Code to.

2. The Authorization server authenticates the Client and verifies that the requested scopes are permitted. 

3. The Resource owner interacts with the Authorization server to grant access.

4. The Authorization server redirects back to the Client with either an Authorization Code or Access Token, depending on the grant type. A Refresh Token may also be returned.

5. With the Access Token, the Client can request access to the resource from the Resource server.

What is OAuth 2.0 and what does it do for you? - Auth0. (n.d.). Auth0. Retrieved June 21, 2022, from https://auth0.com/intro-to-iam/what-is-oauth-2/

### What is a JWT token?
A JSON web token is a secure way of transmitting information between parties through a compact and self-contained JSON object. The information can be trusted and verified because it's digitally signed. JWTs can be signed using a secret or a public/private key.

### When is a Web Token applicable?
JWTs are applicable when your project requires authorization and information. 

They're mostly used for authorization; once the user is logged in through the identity provider, every subsequent request will include the JWT so that the user can access all resources and services their account is allowed to use. The most widely-used feature for JWT's is Single Sign-on.

JWT's are also reliable for information exchange; they can safely transmit information between parties due to being able to protect sensitive data with private claims. Because JWT's are signed, you can verify that the sender of the JWT is who it says it is in the case of tokens signed with a private key

### What is the structure of a JSON web token?
A JSON web token consists of three seperate parts seperated by dots, namely;

- The Header
- The Payload
- The Signature

I'll do my best to sum up each part seperately.

#### Header

The header usually consists of two parts: the token type, which is JWT, and the signing algorithm being uses, such as HMAC SHA256 or RSA.

For example:
```
{
  "alg": "HS256",
  "typ": "JWT"
}
```
Then, this JSON is encoded into Base64Url to form the first part of the JWT.

#### Payload
The second part of the token is the payload, which contains the claims. Claims are statements about an entity (usually the user) and additional data. This is the core of the token because it's where the requested data can be found.
There are three types of claims, namely;

- Registered claims
- Public claims
- Private claims

**Registered claims**

These are a set of predefined claims which are not mandatory but recommended to provide useful, interoperable claims.

Some examples of these are: iss (issuer), exp (expiration time), sub (subject) and aud (audience)

These claim names are only three characters long because a JWT is meant to be compact.

**Public claims**
The best way to describe these is that they can be defined at will by the user of the JWT's. But to avoid collisions, they should be defined as a URI that contains a collision resistant namespace.

**Private claims**
These are the custom claims created to share information between parties that gave their consent on having this information shared.

An example of a payload could be:

```
{
  "sub": "1234567890",
  "name": "John Doe",
  "admin": true
}
```
Then, the payload is encoded into Base64Url to form the second part of the JSON Web Token.

#### Signature
The signature is a bit more tricky - it's created by signing the encoded header and payload, a secret, and the algorithm specified in the header.
So if you'd use the HMAC SHA256 algorithm for example, the signature would be created like this:

```
HMACSHA256(
  base64UrlEncode(header) + "." +
  base64UrlEncode(payload),
  secret)
```

The signature is used to verify the message wasn't changed through it's journey and it can also verify that the sender of the JWT is who it says it is in the case of tokens signed with a private key.

auth0.com. (n.d.). JWT.IO - JSON Web Tokens Introduction. JSON Web Tokens - Jwt.Io. Retrieved June 21, 2022, from https://jwt.io/introduction

### What are the pros of using Auth0?

Auth0 is designed to help developers solve problems like integration of various logging services by implementing an authentication service with the best features set.

Some examples of this include:

- OAuth 2.0 authentication protocol security;
- UI options, both built-in or custom;
- Auth0 Analytics which capture and measure a ton of specific events;
- a huge number of social networks which Auth0 supports;
- detailed documentation and clear code examples in popular programming languages;
- libraries with a large number of technologies;
- a wide range of settings

All this combined makes Auth0 the Identity Service I&#39;m most interested in working with.

# Conclusion

The best way to use a safe identity service for this project is to use a solution that&#39;s got everything regarding security handled, and after researching several examples of this, I&#39;ve decided to use Auth0 2.0.

It doesn't take much time to set up which allows you to use more time and effort figuring out the essential parts of your project while also managing security issues with far more detail than a custom-made login system likely would.

### Sources:
https://www.techtarget.com/searchsecurity/definition/identity-provider

https://www.okta.com/uk/identity-101/why-your-company-needs-an-identity-provider/

https://auth0.com/intro-to-iam/what-is-oauth-2/

https://jwt.io/introduction
