# My Learning Outcomes


## 1. You design and build user-friendly, full-stack web applications

### S3IP Front-end

I&#39;ve decided to use Vue for my front-end due to the pros and cons I could find about of the recommended JavaScript frameworks; although there&#39;s a few problems like a smaller variety of tutorials and plug-ins, it seemed like it was great to work with due to it&#39;s focus on components, making it&#39;s code easy to comprehend by the way it splits everything up in separate files.
 Ironically enough, by the end of the semester it&#39;s actually the JavaScript framework I&#39;d recommend the least; at least for now, due to the upgrade from Vue 2 to Vue 3 still being a bit messy. There&#39;s a lot of plug-ins that haven&#39;t yet made their way to Vue 3 and the lacking amount of tutorials only gets worse with the new version due to that being more recent, meaning you&#39;d generally find more solutions that worked for Vue 2 but not yet for Vue 3, which makes for a very exhausting process if you&#39;re running into errors you can&#39;t figure out yourself. That was probably my biggest obstacle during this semester, but it&#39;s a learning process all the same and I&#39;m glad I managed to make the most of it nevertheless.

The front-end application calls the API services to create posts and get all posts; It pulls all the posts from PostController. It&#39;s a single-page application where the user is able to create posts after logging in through Auth0.
As is expected of Vue applications, I've split up every functionality in it's own seperate component, which in this case is:
- AddPost.Vue, containing the form and function for adding posts to the database.
- IndexPage.Vue, which adds the style expected of the Index to the single-page application.
- NavBar.Vue, which adds the Auth0 login component and shows the user's account data and a logout button when logged in.
- PostList.Vue, which retrieves all posts currently in the in-memory database and adds the tables for each post it retrieves.

### Auth0

I&#39;ve decided to use Auth0 for my authentication service – I used my [Identity Service Research](https://github.com/JulianJ99/Portfolio/tree/main/IP/Research/IdentityServiceResearch)  to reach that conclusion, and have decided that Auth0 seems best because coming up with your own login system means having to keep so many security details in mind that you&#39;d end up spending a ton of time doing something that could be handled more efficiently and reliably.

By clicking the Login button, you&#39;ll be brought to the Auth0 page where you can login through either an Auth0 account or by using your Google account.

![image](https://user-images.githubusercontent.com/84009857/174311338-774ba94e-e723-48d6-99d0-cf9312cedfc7.png) ![image](https://user-images.githubusercontent.com/84009857/174311398-aa40de52-b243-4930-be74-61cb34df3895.png) ![image](https://user-images.githubusercontent.com/84009857/174311434-a4c9abec-9bea-4d90-9fbb-54dbb09eb3e1.png)

### PostCRUD Back-end

The PostCRUD project serves as the back-end – it connects with the Front-end through the usage of Springboot, a backend framework that calls the database on all functions that require the back-end. 
It works alongside the front-end through API requests; PostsDataServices.js in the front-end uses the http links required for these functions to access the functions in the back-end. So when PostDataService.GetAll gets called, it uses GET localhost:8081/api/posts to fetch all posts for the front-end, for example. 
Similarly, creating a new post is done through PostDataService.create(data) (where data uses the post and song strings made by the user, and the username and userimage of the logged-in account) by calling POST localhost:8081/api/posts to add that post to the in-memory repository.

I've set up my back-end project in this way for the sake of a clear structure; due to all functions requiring the same Post model, it seemed best to stick to a single PostController for it's functions.

![image](https://user-images.githubusercontent.com/84009857/174318189-f8d8d8e6-60e3-40ad-8353-c9b766ca16c4.png)

![image](https://user-images.githubusercontent.com/84009857/174318417-8431e15d-8895-4fd9-b82f-e9b0c4c8d253.png)

![image](https://user-images.githubusercontent.com/84009857/174318462-f79f00d2-c03f-4480-a61c-5aedc41bcc59.png)

![image](https://user-images.githubusercontent.com/84009857/174318867-2f2cbaff-99f9-44a8-8e76-ba725cbaaada.png)


## 2. You use software tooling and methodology that continuously monitors and improve the software quality during software development.

To accommodate this learning outcome, I wrote and automated tests for my back-end, PostCRUD. I decided to use the in-memory H2 database to test my Integration tests; the reason I chose a H2 database is because this wouldn&#39;t end up conflicting with turning the projects into Docker images, because a local database would make running the backend and it&#39;s tests through Docker complicated for anyone downloading the project; they&#39;d have to have the database ready locally with the exact table details necessary for it.

### H2 Database

H2 Database is the aforementioned in-memory database that I&#39;ve used for testing purposes. It&#39;s configured to create a database using my Post model in the back-end. To make that happen, I&#39;ve used this code in my application.properties file:

```
spring.datasource.url= jdbc:h2:mem:testdb
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=password
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
# Hibernate ddl auto (create, create-drop, validate, update)
spring.jpa.hibernate.ddl-auto= update
```

### Integration Testing

I decided to apply Integration Tests to my project to check whether or not the back-end could properly connect to the in-memory database, allowing the project&#39;s functionalities to work as expected. Considering the entire project revolves around the database, I felt like this was the most important thing to test.

#### CreatePostTest

![image](https://user-images.githubusercontent.com/84009857/174319023-da6c63a3-6a03-4c70-8644-817ede2415b1.png)

![image](https://user-images.githubusercontent.com/84009857/174311786-7c44c29b-646a-44d2-bbbd-43da9877df62.png)

#### GetAllPostsTest

![image](https://user-images.githubusercontent.com/84009857/174319029-fb586fb4-6773-4863-af1d-1c6db941b768.png)

![image](https://user-images.githubusercontent.com/84009857/174311868-3f1f2354-b1db-45e5-8f34-5f77f6305be6.png)

Unfortunately I did not manage to create any other tests due to time constraints; I decided on integration tests for the aforementioned reason of the database essentially being the core of the project (due to getting and creating posts, the current main features of the project both relying on it) and therefore I felt like integration tests were the best form of testing for this project due to being able to test the back-end functions and their connection to the database at the same time.

### SonarCloud

To ensure that the quality of my code is continuously monitored, I&#39;ve also set up both of my projects on SonarCloud and set it up so that whenever I&#39;d push a new update for one of these projects on Github, it&#39;d immediately be scanned by SonarCloud which would tell me whether there&#39;d be any major issues within 30 minutes.

![image](https://user-images.githubusercontent.com/84009857/174311946-b40778b8-c2fc-4066-81ab-d48f0b27f649.png)


## 3. You design and implement a (semi)automated software release process that matches the needs of the project context.

### CI/CD

For this learning outcome I&#39;ve decided to use Docker – by pulling my Github repositories into Docker, it&#39;s able to generate an image which can be ran using a Docker container; this allows you to start up either of the projects through PowerShell, without needing a code editor to boot these up, which speeds up development by a lot.

[Front-end Docker container](https://hub.docker.com/r/julian99janssen/vue)

[Back-end Docker container](https://hub.docker.com/r/julian99janssen/springboot)

![image](https://user-images.githubusercontent.com/84009857/174311985-838aefad-4486-46a6-a7d0-1716dea5d5a4.png)

![image](https://user-images.githubusercontent.com/84009857/174312019-3087e099-48d7-4759-be7d-bb23921fb163.png)


## 4. You act in a professional manner during software development and learning.

I made sure to actively ask and apply feedback from our teacher for this project, and we talked (nearly) every week on Wednesday where I&#39;d show what I&#39;m currently working on and struggling with. This has definitely helped me engage in this project more productively, due to getting help with certain issues I couldn&#39;t quite figure out on my own due to both Vue and Java being unknown to me before this semester.

I also made sure to use GitHub so that I could easily push my changes between the PC I use at home and the laptop I use at school without having to do so manually. This also allowed me to revert any pushes I made which ended up being incredibly useful at certain points during this project, considering I&#39;ve had to make quite a few changes to the back-end throughout it.

I&#39;ve also made use of the Pomodoro Technique to stay focused while working, which was recommended to me by my teacher. It&#39;s essentially a timer technique that allows you to stay focused by rewarding you with a short break every time the timer runs out. Usually I&#39;d be working for 25 minutes and would then take a break for 5 minutes and repeat that process. It sounds silly, but it helped my concentration a lot.

The site I used for this was https://pomofocus.io/ 

![image](https://user-images.githubusercontent.com/84009857/174319181-d7cf9345-0c7f-4b0c-b15f-967c47b5101c.png)

## Linked repositories: 
[Front-end](https://github.com/JulianJ99/S3IP)

[Back-end](https://github.com/JulianJ99/PostCRUD)
