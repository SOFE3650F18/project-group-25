# Deliverable 1

## Use Cases

#### Student:

​	UC-1 : View content of a course from a previous years and history of attended courses.
​	UC-2 : Subscribe or unsubscribe to courses.
​	UC-3 : Make a team to share files and invite other students.
​	UC-4 : Upload files.
​	UC-5 : View grades and notifications such as messages, team invites, sceduled exams and when course content is uploaded.
​	UC-6 : Customize personal information.

#### Lecturer:

​	UC-7 : Create a new course or a copy from another course.
​	UC-8 : Upload course material.
​	UC-9 : Manage grades for students(inclding providing grade statisitics) and teams.
​	UC-10 : Send mail to students.
​	UC-11 : Set minimum grade policy for course.
​	UC-12 : Manage archives and their visibility to students.
​	UC-13 : Create new teams with ability to insert and remove students from teams and also ability to delete a team.
​	UC-14 : Choose assistant lecturere.

#### System maintainer: 

​	UC-15 : Create backup of system.
​	UC-16 : Restore partial and complete back-ups of a specific data.
​	UC-17 : Limit size of files that lecturer and student uploads and also limit available space for specific course.

#### Administration:

​	UC-18 : Create, delete, update course.
​	UC-19 : Specify minimum students in the course and course lecturers.
​	UC-20 : Set course policies like course prerequisites for students, completed prerequisites of a course and specify department as prerequisite of a course.
​	UC-21 : Retrieve personal information of student and lecturer
​	UC-22 : Enter lecturer information
​	UC-23 : Calculate grades statistics per year, studnet, course, department or a combination of options
​	UC-24 : Bypass requirements to manually enroll a student 
​	UC-25 : Change information contained and maintained by secondary university systems
​	UC-26 : Synchronize with secondary university systems.

### Use Case Models

​	![Use_Case_Diagram.png](https://github.com/SOFE3650F18/project-group-25/blob/master/Deliverable1/Assets/Use_Case_Diagram.png)

## Quality attribute scenarios 

#### Quality attributes: performance, modifiability, availability, usability, security, reliability, efficiency, maintainability

| ID    | Quality Attributes                         | Scenario                                                     | Associated Use Case    |
| ----- | ------------------------------------------ | ------------------------------------------------------------ | ---------------------- |
| QA-1  | Usability                                  | User can perform a desirable task (if they are allowed to) without any hesitation from the system. | All                    |
| QA-2  | Maintainability                            | System should maintain data that is stored.                  | UC- 25, UC- 15         |
| QA-3  | Performance                                | System must respond within 3 seconds to a users request to do a task. | All                    |
| QA-4  | Security                                   | Only administrator can be authorized changes towards courses. | UC- 18, UC- 19, UC- 20 |
| QA-5  | Security, availability, modifiability      | Only administrators can access information about students and lecturers and also modify it. | UC- 21, UC- 22         |
| QA-6  | Maintainability, availability, reliability | Restore backup of data if system failures occur or the system is being updated | UC- 16                 |
| QA-7  | Scalability                                | As more users are added to the system, improved hardware will be required to manage and handle the extensive load put on by the increase in the user count. | UC- 17                 |
| QA-8  | Testability                                | All features should be able to be tested by system maintainers and if applicable, even the users should be able to see if the functionality of desired task is done correctly. | All                    |
| QA-9  | Security                                   | A student views only their grades and no one else can view them except lecturers and administrators. | UC- 5, UC- 9           |
| QA-10 | Usability                                  | Administration uses grades to get grade statistics.          | UC- 23                 |
| QA-11 | Availability                               | Backup system is provided when system is down for maintenance or updating | All                    |



## Constraints

| ID     | Constraints                                                  |
| ------ | ------------------------------------------------------------ |
| CON- 1 | Certain minimum of students must be enrolled in a coarse for the course to given in a semester |
| CON- 2 | A highly reliable database with high storage capacity is required to store the information of students and lecturers. |
| CON- 3 | System must be accessed from browsers like Google Chrome, Firefox, Safari, IE in platforms like , Windows, IOS, Linux, OSX, Android. |
| CON- 4 | High bandwidth is required to upload files to the system and download files from the system. |
| CON- 5 | A minimum of 500 users should be able to access the system at any time simultaneously. |



## Architectural Concerns

| ID    | Concerns                                                     |
| ----- | ------------------------------------------------------------ |
| CRN-1 | Establishing an overall initial system structure             |
| CRN-2 | Leverage the team’s knowledge about Java Web start, JMS framework, Java language, HTML, CSS, node.JS, Angular |
| CRN-3 | Distribute work to members of the development team           |



