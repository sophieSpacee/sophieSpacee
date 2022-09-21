I have been developing for over a year and a half now, working on both personal and professional projects. Here is what I learned:

* When coding, **you never stop learning**, not a day goes by without me learning something new
* **Every piece of code can be improved** and modified an infinite number of times, you just have to know when to stop
* **It is OK to say you don't know**, other developers are here for you, you just need to ask the right question (stackoverflow, github...)

Here is a list of what I have learned during my first 5 months as a developer @Addworking

## Week 20 - 02/07/2022

* I created complex **Regex** to extract data from document using pdf-parse. 
* I implemented **Mindee OCR** to parse data from documents that were scanned or photographed. 
* * We started a new project, a brand new design of our onboarding process, here is what it looks like:
<img width="1924" alt="Capture d’écran 2022-06-29 à 07 52 26" src="https://user-images.githubusercontent.com/72617821/181062881-4c2ab3e8-68e6-4a03-ac07-8f8ddf2bd666.png">

## Week 19 - 01/31/2022

* This week, we want to be able to extract data from documents. I used Mindee OCR for scanned and photographed documents, and **pdf-parse** for original pdf documents. The idea is to get data from those documents, and verify if the document is valid for our platform. Using Regex, we extracted data from documents with pdf-parse, and launched an API call to URSSAF website, checking if the document is valid. The API also gives us more information on the document, which we catch and use for our verifications.  

## Week 18 - 01/24/2022

* I started using **SQL Server** for a new application we are working on. 
* I installed a **husky** command to force eslint and tests before being able to commint and push a branch on github. 

## Week 17 - 01/17/2022

* I wrote **unit tests** for our frontend. I learned how to use Jest with React, how to mock Amplify and how to test render on a web page. Because we are using functional components, we could not test a function within a component. We had to go around and write tests to look for wanted result displayed on our page. For example, instead of checking if the function setError was called, we had to check in the render if the error message we wanted was displayed. 
* I also installed ESLint on our backend projet in node.js and typescript. I configured it and corrected over 2300 errors. Note for later: always install ESLint before starting on a project. 

## Week 16 - 01/10/2022

* I learned about **serverless** solution, we are going to use it with AWS to host our application. 

## Week 15 - 01/03/2022

* We started a new project, an application dedicated to onboard contractors. We are building this project with Typescript / node.js / express for the backend, and Typescript / React for the frontend. I will be working on both backend and frontend with my team. 
* My first task was to implement authentication with **AWS Cognito**. It allows us to have a fully secured login and signup system. With this tutorial, everything went well, I recommend it: https://jafreitas90.medium.com/simple-and-easy-authentication-wepapp-react-cognito-sample-app-915b0dc99e7a

## Week 14 - 12/27/2021

* My team and I are still working on the Back Office for our conformity team. This week, I worked on some design changes and integration. 
* The backoffice went live ! For this project, we are using Heroku for dev, staging and production environment. 

## Week 13 - 12/20/2021

HOLIDAY 

## Week 12 - 12/13/2021

Integrated a page in Backoffice that included :
* A Document List component with 2 tabs, each tabs had to show different documents. One tab showed documents asked by Addworking, the other one showed documents asked by customers. As all those documents came from a single list, I had to sort them out depending on the company who asked for them, and split them into two distinct lists : one where Addworking had asked the document, one for all other documents. 
* A Document Display component with an unknown number of tabs. When the user clicks on a document in the Document List component, the document is displayed in the middle of the page. Some documents have different PDF files to display, each file must be in a different tab. I had to loop on the files list of the document selected and dynamically create a tab per file. 
* A Comment component that allows users to write a comment in a text area and select a visibility option in a dropdown menu. This one was tricky because it is not possible to change the style of the select menu of react bootstrap. I had to integrate the design and use states to change the value of privacy before submitting the comment. 

## Week 11 - 12/06/2021

* I did learn about unit testing in my training, but I never had to implement them until today. My team chose to use Jest to test our backend functions. I started by installing it and my first task was to test our authentication middleware. If an authorization token was present in the headers, and valid of course, the middleware directs the user to the next function. However, if the token is missing or not valid, an error must appear. That's what I worked on beginning of this week. To test this middleware, I had to mock the request and response of my function, as well as the jwt verify return value. I managed to test my middleware successfully.  
* My second challenge this week was to implement an infinite scroll. We have an API that returns 25 results per page, and we wanted to be able to scroll and load the elements as we were going down the list. We also wanted the already uploaded results to stay there. 
*  First, I found a tutorial on how to load a new page when the scroll nearly reaches the end of the results (great tutorial : https://javascript.plainenglish.io/implementing-infinite-scroll-in-react-34b112813de7). This allowed me to load the 25 next results as I reached the bottom of my page. The problem was that my page was only showing the 25 next results, the precedent ones were not displayed anymore. 
*  To change that, I added a "allowConcat" parameter to my API call. If concat(true), the results were added to the existing list of results with a concat function. If concat was false, the list was only returning the 25 first results. This way, when I scroll down, the function that calls the API uses the allowConcat parameter and the results appear smoothly at the bottom of the list. The infinite scroll is now working fine. 

## Week 10 - 11/29/2021

* Carried on integrating APIs in our back office frontend : filter, sorting out, total number of vendors, total number of clients per vendor...
* I learned how to implement DTO on my backend routes, thanks to a colleague who showed me. 

## Week 9 - 11/22/2021

* After the first week into the backoffice, my team realized we needed to all work on the backend and develop all the APIs needed for the frontend to work. 
* I worked on a research API that returned the id and name of vendors that started with a specific character string. I then integrated it into the front, and developed an autocomplete style research bar. Every character added was launching an API call to get more precise information in the dropdown list below. 

## Week 8 - 11/15/2021

* This week, I integrated the first page of our Backoffice. It is a dashboard showing a list of vendors with their information. The user can filter the list on several parameters and sort it out by name or date. As I was waiting for the API to be done, I created a list of fake vendors to be able to dynamically display them on my page. I used a map function to loop on the vendors' list. 

## Week 7 - 11/08/2021

* My first challenge was to implement Google SSO to login into the BackOffice. I found it hard to find a complete tutorial on how to do this with react and node.js, but by mixing up some videos and articles, I managed to make it work. Several options are available, I chose to put a maximum of logic into the backend side. I generated a customized token based on the user's information to make sure the connection was secure. 
* When I was done, I wrote an tutorial about it: https://sophie-grandperrin.medium.com/implement-google-sso-with-reactjs-node-express-and-mongodb-28a9eeb10cd1


![1_QzaMpOtp8uI7OhQ7kvqqJg](https://user-images.githubusercontent.com/72617821/147593724-ef0332e8-b6d0-4527-8aef-0575cb431b5d.gif)



## Week 6 - 11/01/2021

* This week, my team's objective changed. Instead on working on a vendor application, we are asked to create a brand new Back Office for our conformity team. 
* I initiated the backend for the new BackOffice application, installing all packages needed and connecting it to a MongoDB database. 
* We decided to go with Typescript for the backend, I had never used Typescript before so I did some training on it.  

## Week 5 - 10/25/2021

* I read a lot of articles on React best practices and tried to implement them into our react application. Here are some articles I found interesting:
* https://blog.logrocket.com/the-perfect-architecture-flow-for-your-next-node-js-project/
* https://stackoverflow.com/questions/18927298/node-js-project-naming-conventions-for-files-folders
* https://pretagteam.com/question/nodejs-project-naming-conventions-for-files-folders

## Week 4 - 10/18/2021

* This week, I finished integrating all the mock ups for the MVP of a vendor application.


* After finishing the frontend, we implemented json-server to act as a backend in order to integrate fake APIs into our react application and test if the API calls were done well. 

![vendor-demo](https://user-images.githubusercontent.com/72617821/157905093-be0b58a1-d451-4da9-9f94-dd9aa413ab97.gif)



## Week 3 - 10/11/2021

* I learned how to document react components. After some research, my team chose React Styleguidist. I used their documentation to install it and started documenting our first components. The render is really good, by just adding some comment lines in the code, we got an html page with all our components, what they do and how to use them. 
* I integrated Pappers API into the front application. It is an API that checks if a company exists in France based on its name or identification number. I used react-bootstrap/form to display a search input on my page, than I looped on the results to display them in a dropdown list. Everytime the user updated the text input, an API call is launched to Pappers to get the most accurate results possible. It also gives an autocomplete feel. 

## Week 2 - 10/04/2021

* Got my first wireframe to integrate today. It was easier than I expected, good for my self confidence on the first week in a new career. 
* I learned to integrate i18next to translate an application. Really interesting, I published a medium article on it : https://sophie-grandperrin.medium.com/how-to-translate-a-react-application-3b023e853b80

![translation-gif (3)](https://user-images.githubusercontent.com/72617821/147593618-9edec4b7-188b-4e38-960f-0f6e9761fc51.gif)


## Week 1 - 09/27/2021

* Got my first job as a full stack software developer !!! I am super exited to start with Addworking. They just raised funds, so the tech team is growing fast. They were 6 developers before I joined them. I am the first new one to arrive, but we should be 15 by the end of the year. 
* What I love about this job is that I get to start a new project from scratch. The current application was developed using Laravel, and the new CTO wants to switch to React and Node.js. I am part of a newly formed team in charge of developping this new version. I am really happy to be able to use my newly acquired skills in React and Node.js for this job. 
