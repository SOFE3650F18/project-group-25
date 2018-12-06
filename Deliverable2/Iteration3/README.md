# Iteration 3

*In this iteration of the ADD process, the aim is to address quality attribute driver QA - 6.*

## ADD Step 2: Establish Iteration Goal by Selecting Drivers

The goal of this iteration is to focus on the quality attribute QA - 6 where the scenario is ‘ Restore most recent backup of data if system failures occur or the system is being updated’.  So if a update is needed to be done to the system or the system crashes, the most recent data of the system needs to be used temporarily while in the background, the system would be fixed or updated. The drivers are all the ones that were not addressed or partially addressed in the second iteration.

## ADD Step 3: Choose one or more elements of the System to Refine
This scenario is mostly based on availability, backed up data would be available for the system to use while in the background the system is being fixed or updated. This scenario is also slightly addressing the systems ability to be maintainable and reliable. Refinement would need to be done on the following components mentioned in the first iteration:
- Application server
- Database server

## ADD Step 4: Choose One or More Design Concepts that Satisfy the Selected Drivers

| Design decision and location | Rationale and assumption |
|------------------------------| -----------------------|
| Introduce the spare tactic by replicating the application server and database server | If we replicate the deployment components application server and database server then the system can use the duplicated components to run the system while the system is being repaired or updated in the background. With the spare tactic, a standby system is used for a clients workstation where if the system fails then the client is moved into the standby system where the user will work until the main system is repaired or updated. |
| Introduce rollback tactic to the application server and database server | Rollback will revert to a previous state when the system was in a good state or condition. This is a good tactic as the components or areas with errors are not present and they can be fixed while the user is in the “rollback line” or rollback state. This would work if the rollback happens in a standby system where the standby system integrates the rollback tactic and implements all the components and data from when the system was in a good state and the main system would be fixed while the user is in the standby system. |


## ADD Step 5: Instantiate Architectural Elements, Allocate Responsibilities, and Define Interfaces
| Design decisions and location | Rationale |
| ----------------------------- | --------- |
| Using spare and rollback | Incase of a failure in the system or update being needed, the system would need to go through repairation but a standby system(QA - 6, QA - 11) is needed as a spare in those cases so the rollback tactic will be used to make sure the standby system runs in the same way the main system ran when it was in a good state. Two application servers would need to be built where every time the main system is in a good state, the data is saved(QA- 2) and passed onto standby systemso that its ready to be used when needed. |
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

<a href="https://github.com/SOFE3650F18/project-group-25/projects/6?fullscreen=true">Click here for this iteration's analysis</a>
