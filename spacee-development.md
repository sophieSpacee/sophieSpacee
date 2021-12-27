# My first year as a software developer 

After 5 years as a workplace consultant, I took a full time training for 6 months to become a full stack developer with OpenClassrooms. After I finished my training, I started working on a personal project: a software for real estate professionals. This software allows anyone to create a building and fill it up with teams, collaborative spaces and services. The end goal is to help companies find the best set up according to their synergies and constraints. After two months spent on my project, I got a job at Addworking, a startup company that develops a subcontractor management platform. 

## Week 19 - 12/20/2021

HOLIDAY 

## Week 18 - 12/13/2021

Integrated a page in Backoffice that included :
* A Document List component with 2 tabs, each tabs had to show different documents. One tab showed documents asked by Addworking, the other one showed documents asked by customers. As all those documents came from a single list, I had to sort them out depending on the company who asked for them, and split them into two distinct lists : one where Addworking had asked the document, one for all other documents. 
* A Document Display component with an unknown number of tabs. When the user clicks on a document in the Document List component, the docuemnt is displayed in the middle of the page. Some documents have different PDF files to display, each file must be in a different tab. I had to loop on the files list of the document selected and dynamically create a tab per file. 
* A Comment component that allows users to write a comment in a text area and select a visibility option in a dropdown menu. This one was tricky because it is not possible to change the style of the select menu of react bootstrap. I had to integrate the design and use states to change the value of privacy before submitting the comment. 

## Week 17 - 12/06/2021

* I did learn about unit testing in my training, but I never had to implement them until today. My team chose to use Jest to test our backend functions. I started by installing it and my first task was to test our authentication middleware. If an authorization token was present in the headers, and valid of course, the middleware directs the user to the next function. However, if the token is missing or not valid, an error must appear. That's what I worked on beginning of this week. To test this middleware, I had to mock the request and response of my function, as well as the jwt verify return value. I managed to test my middleware successfully.  
* Implemented an infinite scroll on a list of results. 

## Week 16 - 11/29/2021

* Integrated APIs in frontend 
* Used DTO on backend routes 

## Week 15 - 11/22/2021

* Created APIs for the BackOffice 

## Week 14 - 11/15/2021

* Integrated first page of Backoffice 

## Week 13 - 11/08/2021

* Implemented Google SSO front and back 

## Week 12 - 11/01/2021

* Initiated backend for a new BackOffice application 
* Connected application to MongoDB database 
* Learned how to use Typescript 

## Week 11 - 10/25/2021

* Refacto
* Swithed front to dark mode theme 

## Week 10 - 10/18/2021

* Implement json-server to act as a backend 

## Week 9 - 10/11/2021

* I learned how to document react components. After some research, my team chose React Styleguidist. I used their documentation to install it and started documenting our first components. The render is really good, by just adding some comment lines in the code, we got an html page with all our components, what they do and how to use them. 
* I integrated Pappers API into the front application. It is an API that checks if a company exists in France based on its name or identification number. I used react-bootstrap/form to display a search input on my page, than I looped on the results to display them in a dropdown list. Everytime the user updated the text input, an API call is launched to Pappers to get the most accurate results possible. It also gives an autocomplete feel. 

## Week 8 - 10/04/2021

* Got my first wireframe to integrate today. It was easier than I expected, good for my self confidence on the first week in a new career. 
* I learned to integrate i18next to translate an application. Really interesting, I published a medium article on it : https://sophie-grandperrin.medium.com/how-to-translate-a-react-application-3b023e853b80

## Week 7 - 09/27/2021

* Got my first job as a full stack software developer !!! I am super exited to start with Addworking. They just raised funds, so the tech team is growing fast. They were 6 developers before I joined them. I am the first new one to arrive, but we should be 15 by the end of the year. 
* What I love about this job is that I get to start a new project from scratch. The current application was developed using Laravel, and the new CTO wants to switch to React and Node.js. I am part of a newly formed team in charge of developping this new version. I am really happy to be able to use my newly acquired skills in React and Node.js for this job. 

## Week 6 - 09/20/2021

Building display dynamically  

## Week 5 - 09/13/2021

* Now that I know how to use Context with React (what an amazing tool!), I can access my teams and spaces everywhere on my page. I can focus on creating the dynamic display of teams and spaces on my left component, which represents my building. Once I create a team or a meeting space in my bottom-right table, I want it to appear immediately on the first floor of my building. 
* I used react-dnd to make sure that my users could easily drag and drop spaces from one floor to another. When a space is created, a box appears in my building, its size is dynamic, and depends on which floor it is placed into. If the floor is not full, the size of the box is a simple calculation of the space's surface on the total floor surface. If the floor is full, and the sum of all spaces placed on that floor is greated then the total floor surface, the floor's border becomes red, and the box size calculation changes, it is now a proportion of the space's surface on the total spaces' surfaces on that same floor. That way, there is no overflow, and the proportions are respected. 
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


