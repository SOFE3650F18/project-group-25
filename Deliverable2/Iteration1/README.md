# Iteration 1

*This section presents the results of the activities that are performed in each of the steps of ADD in the first iteration of the design process.*

## ADD Step 1: Review Inputs

The first step of the ADD method involves reviewing the inputs and identifying which requirements will be considered as drivers (i.e., which will be included in the design backlog). The inputs are summarized in the following table.

| Category                        | Details                                                      |
| ------------------------------- | ------------------------------------------------------------ |
| Design purpose                  | This is a greenfield system from a mature domain. The system is new but is based off of existing patterns and styles. |
| Primary functional requirements | From the use cases above, the primary ones are:<li>UC - 1: Because it supports the core business <li> UC - 7: Because it supports the core business <li>UC - 8:  Because it supports the core business. <li>UC - 9: Because it supports somewhat administrative functions for the lecturers and administrators can even use those functions. <li>UC - 10: Because it supports core business. <li>UC - 15: Because it supports back up of historical data. <li>UC - 16: Because it supports fetching backed up data. <li> UC - 18: Because it supports administrative functions for administrators. <li> UC - 20:  Because it supports administrative functions for administrators. |
| Quality attribute scenarios     |                                                              <table><tr><th>Scenario ID</th><th>Importance to customer </th><th>Difficulty to implement according to architecture</th></tr><tr><td>QA-1</td><td>High</td><td>Medium</td></tr><tr><td>QA-2</td><td>High</td><td>High</td></tr><tr><td>QA-3</td><td>Medium</td><td>High</td></tr><tr><td>QA-4</td><td>High</td><td>Medium</td></tr><tr><td>QA-5</td><td>High</td><td>Medium</td></tr><tr><td>QA-6</td><td>High</td><td>High</td></tr><tr><td>QA-7</td><td>Medium</td><td>Medium</td></tr><tr><td>QA-8</td><td>Medium</td><td>Low</td></tr><tr><td>QA-9</td><td>High</td><td>Low</td></tr><tr><td>QA-10</td><td>Medium</td><td>Low</td></tr><tr><td>QA-11</td><td>High</td><td>High</td></tr></table><br>Quality attributes QA - 1, QA - 2, QA - 4, QA - 5, QA - 6, QA - 7, and QA - 11 are selected as drivers.|
| Constraints                     | All constraints discussed are included as drivers.           |
| Concerns                        | All concerns discussed are included as drivers.              |

## ADD Step 2: Establish Iteration Goal by Selecting Drivers

**The goal of this iteration is to design the CMS system. Regarding the CMS system, the following drivers should be kept in mind throughout the iterations:*

**Selected drivers for QA:**

​	QA - 1: Usability 
​	QA - 2: Maintainability
​	QA - 4: Security
​	QA - 5: Security, availability, modifiability
​	QA - 6: Maintainability, availability, reliability
​	QA - 7: Scalability
​	QA - 11: Availability 

**Selected drivers for constraints (CON):**	

​	CON- 1: Certain minimum of students must be enrolled in a coarse for the course to given in a semester 

​	CON - 2: A highly reliable database with high storage capacity is required to store the informations of students and lecturers. 

​	CON - 3: System must be accessed from browsers like Google Chrome, Firefox, Safari, IE in platforms like , Windows, IOS, Linux, OSX, Android.

​	CON - 4: High bandwidth is required to upload files to the system and download files from the system.

​	CON - 5: A minimum of 500 users should be able to access the system at any time simultaneously. 

**Selected drivers for concerns (CRN):**

​	CRN - 1: Establishing an overall initial system structure.

​	CRN - 2: Leverage the team’s knowledge about various programming languages.

​	CRN - 3: Distribute work to members of the development team


## ADD Step 3: Choose One or More Elements of the System to Refine

*Since this is a greenfield development effort, the element to refine is the CMS. The refinement would be performed through decomposition.* 

![ss](https://github.com/SOFE3650F18/project-group-25/blob/master/Deliverable2/Iteration1/Assets/diagram_1.png)

## ADD Step 4: Choose One or More Design Concepts That Satisfy the Selected Drivers


| Design decisions and location | Rationale |
|------------------------------ |-----------|
| Layered pattern | This can be used to structure the system so its divided into many groups. Each layer would provide service for the next higher layer. Testability, maintainability, abstraction and encapsulation are guaranteed.<br> <br>There could be a presentation, logic and data layer where the user wanted to fetch a file from the CMS (UC - 1), then the logic layer which will communicate the users request to the database, the data layer will fetch the file that was backed up (UC - 15) and send it through the logic layer to the presentation layer for the user to see.<br><br>Could also use MVC pattern.|
| Logically structure the messaging mechanism with Publish - subscribe pattern | This pattern helps a publisher message a subscriber (UC - 10). In the CMS systems case, the publisher can be the lecturer or a team member of a team and the subscriber can be a lecturer or another member in the class or a team member.  |
| Physically structure using 3 tier deployment | Since the CMS should be accessible from a web browser (CON -3), and data needs to be backed up and data must be fetched from a storage device (CON -2), a database server is needed so this deployment pattern is appropriate. |
| Logically structure the server part of the system using Event driven architecture | It is highly scalable and highly adaptable for small applications and big. <br><br>When the CMS system crashes or needs to be updated that is an event and what the system would need to do is use backup data to run the system (UC - 16) while in the background the system is being fixed or updated. The database would listen for the system to say that it has crashed or needs to be updated and the database sends backup data for the system to run while the system is going through maintenance. So the system can work and also perform maintenance at the same time. |
| Logically implement the system using Web application reference architecture to the client side of the system | The application would be accessed through a browser in the client side (CON - 3)  so the client side of this system can be implemented using web application reference structure. <br><br>The bulk of the application resides on the server, and its architecture has presentation layer, business layer and data layer. And this is best since users can access CMS in the browser. The user can access data from the presentation level and the data layer will fetch the data if they are authorized to which the business layer would handle (UC- 1, QA - 1, QA - 4, CON - 4, CRN - 2).<br><br>Data can be accessed by the server of the CMS system (UC - 16) and the business layer (business logic component) will put business rules upon the application data which’ll make sure data is not accessible by unauthorized personals. <br><br>Web application can be accessed from many platforms using a standard web browser. <br><br>We disregarded rich client architecture because the application is run on the user computer by installing into their computer and running it which the CMS system does not need to do. Mobile application reference architecture was also disregarded because it typically is executed on handheld devices which is not the goal of the CMS system because it a browser based and for many different types of browsers. Also a mobile application has screen limitations and is less portable.  |
| Logically structure the server side of the CMS system using the service application | Service application does not need a presentation layer which is an advantage instead it exposes services that are consumed by other application. So in the server side the service could be to send or fetch data, also keep backing up data. |


## ADD Step 5: Instantiate Architectural Elements, Allocate Responsibilities, and Define Interfaces

No interface decisions can be made at this time. 

## ADD Step 6: Sketch Views and Record Design Decisions

The diagram below shows the two reference architectures that were selected for client and server applications.<br>

![ss](https://github.com/SOFE3650F18/project-group-25/blob/master/Deliverable2/Iteration1/Assets/ref_architecture_1.png)

*Client side:* 

| Element | Responsibility |
| --------|----------------|
|Browser| Web browser would be running on the client machine be it the student, lecturer or administrator.|
| User interface | This component has UI elements like buttons and text fields and they receive user interactions and present information to the user.|
|UI process logic|Responsible for data validation, orchestrating interactions with business logic, and provide data that is coming from the business layer to the user interface components. |
|Business logic|Retrieves and processes application data and applies business rules on the data. |
|Business entities|These components represent the entities from the business domain and their associated business logic.|
|Data access|Encapsulate persistence mechanisms and provide common operations used to retrieve and store information.|
|Helpers and utilities|These components contain functionality common to other modules in the data layer but not specific to any of them. |
|Service agents|Attract communication mechanisms used to transfer data to external services. |
|Security| Handles security aspects like authorization and authentication. |
| Operation management|These components handle exception management, logging and instrumentation and validation. |
|Communication|Handles communication mechanisms across layers and the tiers. |

*Server Side:*


| Element              | Responsibility                                               |
| -------------------- | ------------------------------------------------------------ |
| Service interfaces   | Responsible for exposing services that are consumed by the components that run on the browser. |
| Message types        | Manages the types of messages send between client and server. |
| Business logic       | Retrieves and processes application data and applies business rules on the data. |
| Business entities    | These components represent the entities from the business domain and their associated business logic. |
| Data access          | Encapsulate persistence mechanisms and provide common operations used to retrieve and store information. |
| Security             | Handles security aspects like authorization and authentication. |
| Operation management | These components handle exception management, logging and instrumentation and validation. |
| Communication        | Handles communication mechanisms across layers and the tiers. |

**The diagram below shows the deployment of where the components of the modules shown above will be deployed. **

![ss](https://github.com/SOFE3650F18/project-group-25/blob/master/Deliverable2/Iteration1/Assets/ref_architecture_2.png)


| Element            | Responsibility                                               |
| ------------------ | ------------------------------------------------------------ |
| User browser       | The user's browser where the client side of the system will be hosted. |
| Application server | Server that hosts server side of the system and also serves web pages. |
| Database server    | Server that hosts legacy relational database.                |

| Relationship                                   | Description                                                  |
| ---------------------------------------------- | ------------------------------------------------------------ |
| Between application server and database server | Communication with the database will be done using PostgreSQL. |



## ADD Step 7: Perform Analysis of Current Design and Review Iteration Goal and Achievement of Design Purpose

![ADD PROJECT BOARD IMAGE](https://github.com/SOFE3650F18/project-group-25/blob/master/Deliverable2/Iteration1/Assets/step7.png)
test