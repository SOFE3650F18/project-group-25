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

![it_3_step_6](https://github.com/SOFE3650F18/project-group-25/blob/master/Deliverable2/Iteration3/Assets/it_3_step_6.png)

| Element | Responsibility |
| --------| ---------------|
|Standby System| This will replicate the main system and be a spare incase of a fault in the main system. If the main system has a fault, it will finds its data from when the system was in a good state (rollback) and it will send that data to be replicated into the standby system so it can run while the main system would be repaired. |
| Fault sensor | This will sense if there's a fault in the main system if there is then the standby system will run. |

![it_3_step_6_seq](https://github.com/SOFE3650F18/project-group-25/blob/master/Deliverable2/Iteration3/Assets/it_3_step_6_seq.png)

The sequence diagram above shows a scenario where if the main system had any faults or needs to be updated, how would the physical nodes communicate with each other.

## ADD Step 7: Perform Analysis of Current Design and Review Iteration Goal and Achievement of Design Purpose
In this iteration, important decisions were made to QA - 6 which would also impact QA - 2 who’s scenario was to keep a backup of the data. The table below shows the different drivers and the decisions that were made during the iteration. Drivers that were completely addressed in the previous iteration are not in the table.

<a href="https://github.com/SOFE3650F18/project-group-25/projects/5?fullscreen=true">Click here for this iteration's analysis</a>