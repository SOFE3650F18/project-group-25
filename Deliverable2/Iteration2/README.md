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
| Logically implement the system using Web application reference architecture to the client side of the system | Web application can be accessed from many platforms using a standard web browser. <br>We disregarded rich client architecture because the application is run on the user computer by installing into their computer and running it which the CMS system does not need to do. Mobile application reference architecture was also disregarded because it typically is executed on handheld devices which is not the goal of the CMS system because it a browser based and for many different types of browsers. Also a mobile application has screen limitations and is less portable. 
 |
| Use of the MVC architecture design pattern | Using the MVC will be useful since it will allow users to navigate through the pages and information while the server listens for event listeners in the controller and Javascript which handels user request, meanwhile the views will be the top layer responsible for showing user the content. Model layer will be responsible for data in the database.
 |