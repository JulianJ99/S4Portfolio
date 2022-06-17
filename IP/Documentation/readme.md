# My documentation

## Table of Contents
[User Stories](https://github.com/JulianJ99/Portfolio/tree/main/IP/Documentation#user-stories)

[Domain Model](https://github.com/JulianJ99/Portfolio/tree/main/IP/Documentation#domain-model)

[C4 Model](https://github.com/JulianJ99/Portfolio/tree/main/IP/Documentation#c4-model)

## User Stories

User Stories are a general explanation of a functionality written from the perspective of a user – it helps put into perspective how a feature will provide value to the user.

At the start, I&#39;ve written a lot of User Stories that sounded like a good idea for a Social Media platform like my application, namely:

As user, I want to able to create an account so that I can use any functionalities that require authentication

As user, I want to be able to log in so that I can access the account I created

As user, I want to see an overview of all posts created on the homepage so that I can interact with the other users

As user, I want to create posts to communicate with other users

As user, I want to add Spotify-links to my posts so the music I want to recommend other users shows up in my posts.

As user, I want to react to posts so that I can converse with other users.

As user, I want to send friend requests so I can add other users as friends.

As user, I want to accept friend requests so I can add other users as friends.

As user, I want to be able to deny friend requests from users I&#39;d rather not have as friends.

As user, I want to be able to make my account private so only friends can see my posts.

As admin, I want to be able to delete accounts that aren&#39;t adhering to the rules.

As admin, I want to be able to delete posts that aren&#39;t adhering to the rules (by spreading hate for example, anything that isn&#39;t allowed or on topic for the current demographic)

Eventually, I decided to hone in on four user stories and fully focus on making a good basis for the application that can eventually be expanded on. 
### The user stories I decided on were:

As a user, I want to be able to create an account so that I can use functionalities that require authentication.

As user, I want to be able to log in so that I can access the account I created.

Acceptance criteria: This has to be done through Auth0. Users can make an Auth0 account or log in with their own Google account.

As user, I want to create posts to communicate with other users

As user, I want to add Spotify-links to my posts so the music I want to recommend other users shows up in my posts.

Acceptance criteria: User&#39;s name and profile image has to be added to the post to let other users know who posted that post.

## Domain Model

The domain model is the concept of the domain that makes use of both behaviour and data. It&#39;s essentially a first sketch of the classes necessary to make the project work, which in this project&#39;s case makes for a pretty meagre amount of classes, but the relationships between them is still important to pay attention to in all stages of the project.

![image](https://user-images.githubusercontent.com/84009857/174319666-06d67908-3390-4318-8c53-34228220acd5.png)

# C4 Model

### Level 1; System Context diagram

![image](https://user-images.githubusercontent.com/84009857/174319657-b60c51c2-6fde-494b-8573-9a409d322b11.png)

The C1 model is a System Context diagram meant to help you step back and see the big picture, and as a result it&#39;s a great starting point for diagramming and documenting a software system. Here&#39;s where you can see how I had originally planned my project to work; by giving administrators a separate frontend where they&#39;d have all of their administrative features. I eventually had to drop RBAC (Role-Based Access Control) due to time constraints.

### Level 3; Component Diagram

![image](https://user-images.githubusercontent.com/84009857/174319661-d0ba1fba-207f-47d0-9653-0829ad4f60aa.png)

The C3 Model is all about zooming in and decomposing every container further to identify the major structural building blocks and their interactions. In this case, considering the back-end uses one controller, I&#39;ve decided to zoom in on that one and see how it&#39;s functions are expected to work with the database and what it sends/receives from it.

## Sources:

[https://c4model.com/](https://c4model.com/)
