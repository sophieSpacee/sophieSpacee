# Spacee - workplace optimization software

I am currently working on a software for real estate professionals. This software allow you to create a building and fill it up with teams, collaborative spaces and services. The end goal is to help you find the best set up according to your synergies and constraints. You can find bellow details on my journey:

## Week 4

* Now that my user can create a project, and access all his projects through his dashboard page, it's time to get serious. I started working on the most important page of my software, the project dashboard. This page is the center of my tool, it's where magic happens. It needs to be 100% user friendly.
* I started with the easy but not so easy part: frontend. Lots of different components on this page as display is different depending on what stage the user is on. 

![image](https://user-images.githubusercontent.com/72617821/133153391-e2ca936c-24a5-487b-9519-4348a900fa0f.png)

* I integrated the general page layout first, and focused on the bottom-right-hand-side component that includes 3 different tabs. Those tabs interact with the building frame on the left-hand-side.
* First, I coded the three different tabs, with associated pop up and table display. I used a popup component called react Modal.

![image](https://user-images.githubusercontent.com/72617821/133153956-fea108cf-8f04-49dd-8006-a40d3816ac03.png)

* Now I am working on the backend side of this page. I need to learn how to use Context in order to share my teams and spaces data with my building component. I heard about Redux, but my mentor from OpenClassrooms told me Context was easier to learn. 
* After a couple of tutorials and some documentation reading, I managed to implement context to share my project details into all my project components. 

## Week 3

* Now that my user is logged in safely, I can start working on my actual tool. The first step is for my user to create a project. He needs to complete a couple of information about his building: project name, building address and a list of floors. 
* I started working on the frontend of that page, integrating the design was easy, except for the bootstrap table... Aligning items was hard, adding a delete button was not that easy, but I did it. It was the first time I used an array as a state variable. A bit tricky but it went well. 
* I created a Project model. For each project, there is a name, an address, and an array of floors. Each project is linked to a user thanks to the userId.
* I developed the backend routes to create a project once the user submit the "new project" form. 
* I wanted to use Google Map Autocomplete API to fill out my address input, it was way more complicated then Sengrid. After a day of reading all tutorials I could find, I finally realised the problem did not come from my code, but from the fact I did not enter my credit card details into my GCP account... Once that was solved, everything went fine. It took me an hour to use Static Google Map to draw a map canvas of my project location on my dashboard page. 
* Looks great:

![image](https://user-images.githubusercontent.com/72617821/133152097-a206913b-c0f9-4670-9664-70dd9989ddc2.png)


## Week 2

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


