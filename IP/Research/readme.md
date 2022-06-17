# Research – Identity service

## Problem definition

Programming projects often need an identity service; and it is of utmost importance to make sure this is set up well, for the sake of user safety. Therefore, I&#39;m interested in researching what would be the best way to set up an Identity Service for my current project

# Main question: How do I set up a identity service for my project?

## Sub questions

### What is Identity service?

Identity-as-a-Service, or IDaaS, refers to a wide variety of cloud-hosted services for identity and access management (IAM). Essentially, IDaaS is a category of technological functions that have to do with user identity and are hosted in the cloud. IDaaS providers help ensure that users are who they claim to be, ultimately blocking cyber criminals and other unauthorized users from accessing sensitive data.

### What does user safety entail?

User safety means taking the best measures possible against attempts to hack the system. By being able to breach the database easily, hackers could leak user credentials and access their accounts through that information; which could potentially lead to a lot more information of the user being leaked (like them using multiple passwords on different sites, for example)

### What would be the best way to make an Identity Service?

The best way to make a login system is to use a flexible, drop-in solution that adds authentication and authorization services to your applications. You _could_ make it yourself, but there&#39;s so much security details you&#39;d have to keep in mind that you&#39;d be spending a ton of time doing something that could be handled a lot more reliably. A notable example of these solutions is Auth0.

## What are the pros of using Auth0?

Integration of various logging services can cause many problems and increase the number of potential risks to data security and Auth0 is designed to help developers solve this problem by implementing an authentication service with the best features set.

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

The best way to use a safe identity service for this project is to use a solution that&#39;s got everything regarding security handled, and after researching several examples of this, I&#39;ve decided to use Auth0.

#### Sources:

[https://auth0.com/docs/get-started/auth0-overview](https://auth0.com/docs/get-started/auth0-overview)

[https://www.cloudflare.com/learning/access-management/what-is-identity-as-a-service/](https://www.cloudflare.com/learning/access-management/what-is-identity-as-a-service/)

[https://agilie.com/en/blog/reasons-to-use-auth0-for-authentication-in-your-application](https://agilie.com/en/blog/reasons-to-use-auth0-for-authentication-in-your-application)
