# My Spacee Project

After 5 years as a workplace consultant, I decided to launched a product to improve user experience during a real estate project. I quit my job and took a full time training for 6 months to become a full stack developer with OpenClassrooms. When I finished my training, I started working on my idea: a software for real estate professionals, Spacee (https://spacee-workplace.com/). 

## Week 7 - 09/27/2021
* This week, I deployed my MVP. I used RemoteMySql.com to host my database for free. I used Heroku to host and deploy my frontend and backend projects. It is now online, and people can test it. I am so happy. After months of designing, thinking, structuring, my project is finally online, usable. It is not finished of course, I still have to implement the synergy logic, but it is enough to have people test it and give me feedback. 
* Great timing because in 2 days, I start my new job at Addworking as a full stack developer, and I won't have as much time to spend on this project. 
* Here is what it looks like: 

![spacee-workplace-demo](https://user-images.githubusercontent.com/72617821/191592368-1b6c23f9-43e1-4fc3-a9fd-5e4d62397442.gif)

https://www.youtube.com/watch?v=kGts8f_sfpE

## Week 6 - 09/20/2021

* Last piece of development to have my MVP ready is to be able to link a space to a floor or another space. It is the synergy part of my product. A user can link two teams together if they work a lot with each other and need to be positioned on the same floor. Same goes between a team and a specific space (laboratory, training room etc). I also would like for a space to be locked to a specific floor (cafeteria, welcome desk...) if the building has constraints, it is important to include them in the software from the beginning. 
* I decided to have an action box displayed when the user hovers on a team or space on the building component. Some space were too small, and the space box would have been crowed if I added information or button inside it. 

 ![Headquarter-hover](https://user-images.githubusercontent.com/72617821/147593275-25ed07ac-8e03-49c9-9194-0a0a4643b6e6.jpg)

## Week 5 - 09/13/2021

* Now that I know how to use Context with React (what an amazing tool!), I can access my teams and spaces everywhere on my page. I can focus on creating the dynamic display of teams and spaces on my left component, which represents my building. Once I create a team or a meeting space in my bottom-right table, I want it to appear immediately on the first floor of my building. 
* I used react-dnd to make sure that my users could easily drag and drop spaces from one floor to another. When a space is created, a box appears in my building, its size is dynamic, and depends on which floor it is placed into. If the floor is not full, the size of the box is a simple calculation of the space's surface on the total floor surface. If the floor is full, and the sum of all spaces placed on that floor is greater then the total floor surface, the floor's border becomes red, and the box size calculation changes, it is now a proportion of the space's surface on the total spaces' surfaces on that same floor. That way, there is no overflow, and the proportions are respected. 
* When a space box is dragged and dropped to another floor, the space's floor is changed in the database. This way, the database is always up to date, and the user's work cannot be lost. 

![ggif-dnd](https://user-images.githubusercontent.com/72617821/146988160-c5764ff0-9428-4276-b1e4-0ddd738c3e59.gif)

## Week 4 - 09/06/2021

* Now that my user can create a project, and access all his projects through his dashboard page, it's time to get serious. I started working on the most important page of my software, the project dashboard. This page is the center of my tool, it's where magic happens. It needs to be 100% user friendly.
* I started with the easy but not so easy part: frontend. Lots of different components on this page as display is different depending on what stage the user is on. 

![image](https://user-images.githubusercontent.com/72617821/133153391-e2ca936c-24a5-487b-9519-4348a900fa0f.png)

* I integrated the general page layout first, and focused on the bottom-right-hand-side component that includes 3 different tabs. Those tabs interact with the building frame on the left-hand-side.
* First, I coded the three different tabs, with associated pop up and table display. I used a popup component called react Modal.

![image](https://user-images.githubusercontent.com/72617821/133153956-fea108cf-8f04-49dd-8006-a40d3816ac03.png)

* Now I am working on the backend side of this page. I need to learn how to use Context in order to share my teams and spaces data with my building component. I heard about Redux, but my mentor from OpenClassrooms told me Context was easier to learn. 
* After a couple of tutorials and some documentation reading, I managed to implement context to share my project details into all my project components. 

## Week 3 - 08/30/2021

* Now that my user is logged in safely, I can start working on my actual tool. The first step is for my user to create a project. He needs to complete a couple of information about his building: project name, building address and a list of floors. 
* I started working on the frontend of that page, integrating the design was easy, except for the bootstrap table... Aligning items was hard, adding a delete button was not that easy, but I did it. It was the first time I used an array as a state variable. A bit tricky but it went well. 
* I created a Project model. For each project, there is a name, an address, and an array of floors. Each project is linked to a user thanks to the userId.
* I developed the backend routes to create a project once the user submit the "new project" form. 
* I wanted to use Google Map Autocomplete API to fill out my address input, it was way more complicated then Sengrid. After a day of reading all tutorials I could find, I finally realised the problem did not come from my code, but from the fact I did not enter my credit card details into my GCP account... Once that was solved, everything went fine. It took me an hour to use Static Google Map to draw a map canvas of my project location on my dashboard page. 
* Looks great:

![image](https://user-images.githubusercontent.com/72617821/133152097-a206913b-c0f9-4670-9664-70dd9989ddc2.png)


## Week 2 - 08/23/2021

* I wanted to update my website by adding tutorials on how to use Spacee and what should be done before using it. I could have used React, but it is not the best for SEO, instead I cheated and downloaded a sexy template, just adapted the html to fit my needs. I did not know how to deploy it, a friend of mine helped me, he used an AWS instance, nginx for the web server and letsencrypt for the SSL. My website : https://spacee-workplace.com  
* I started working on the "forgot my password" flow, designing several pages (password recovery, change password, confirmation password change)
* The frontend was easy, but it was the first time I had to add this feature on the backend side, fortunately I found a tutorial on Youtube that explained how to use JWT in that particular case
* Another issue was to find a way to send an email, I had never done it. I decided to use Sengrid, it was surprisingly easy using their documentation. 
* Here is what the email looks like: 

![image](https://user-images.githubusercontent.com/72617821/133149358-62f05d83-8f61-47d3-adea-3909d0ef01b4.png)

## Week 1 - 08/16/2021

* I decided to build my project using ReactJS with Bootstrap and Sass for my frontend, Node.js, express, Sequelize with a MySQL database for my backend. 
* I had my figma design made by a friend (my first attempt at making them myself was a fail)
* I initiated my React project and organized it with a simple structure: assets, pages, components, style
* I developed the frontend pages for User signin, signup along with the corresponding backend routes
* I decided to use bcrypt to hash user password and I encrypted the user email using CryptoJS with base64, that way neither password or email are sent clear through the network

![image](https://user-images.githubusercontent.com/72617821/133149150-9a4fd140-833e-4995-ae32-13f206e6130e.png)


