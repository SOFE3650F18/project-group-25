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
