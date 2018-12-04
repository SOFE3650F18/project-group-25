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

