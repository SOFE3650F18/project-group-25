# Iteration 2

*In this iteration of the ADD process, the aim is to identifying Structures to Support Primary Functionality.*

## ADD Step 2: Establish Iteration Goal by Selecting Drivers

The goal is to address all the other drivers and to do this, the frontend of the system needs to be established.

## ADD Step 3: Choose one or more elements of the System to Refine
The elements to be refined in this iteration are the client side module from the previous iteration using decomposition. 

## ADD Step 4: Choose One or More Design Concepts that Satisfy the Selected Drivers
| Design decisions and location | Rationale and assumptions |
|-------------------------------|------------------------|
| Build the UI of the client side using Angular | Angular ensures security( QA -4, QA - 5). React would be an alternative but its level of security is poor.  |
| Logically implement the system using Web application reference architecture to the client side of the system | Web application can be accessed from many platforms using a standard web browser. <br>We disregarded rich client architecture because the application is run on the user computer by installing into their computer and running it which the CMS system does not need to do. Mobile application reference architecture was also disregarded because it typically is executed on handheld devices which is not the goal of the CMS system because it a browser based and for many different types of browsers. Also a mobile application has screen limitations and is less portable. |
| Use of the MVC architecture design pattern | Using the MVC will be useful since it will allow users to navigate through the pages and information while the server listens for event listeners in the controller and Javascript which handels user request, meanwhile the views will be the top layer responsible for showing user the content. Model layer will be responsible for data in the database.|

## ADD Step 5: Instantiate Architectural Elements, Allocate Responsibilities, and Define Interfaces

| Design decisions and location | Rationale  |
|------|-----|
| Angular prevents XSS | XSS (cross site scripting) is when an attacker can inject a client side script into web page that is viewed by other users which can steal user data and also impersonate a user. Angular treats all values that are inserted as untrusted by default and sanitizes and escapes untrusted values (QA - 5).|
| Use a javascript functionality to make HTTP and RESTful API calls to the server | These will allow us to not only obtain data through the API call to server, but will allow us to trigger different instance of the views on the client side. This can be done by DOM manipulation and event listeners and calling the server to retrieve information. (QA-1, QA-5) |
## ADD Step 6: Sketch Views and Record Design Decisions

![client_server_MVC](https://github.com/SOFE3650F18/project-group-25/blob/master/Deliverable2/Iteration2/Assets/client_server_MVC.png)

## ADD Step 7: Perform Analysis of Current Design and Review Iteration Goal and Achievement of Design Purpose

<a href="https://github.com/SOFE3650F18/project-group-25/projects/5?fullscreen=true">Click here for this iteration's analysis</a>