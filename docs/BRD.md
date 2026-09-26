

# **Business Requirements Document(BRD) Template**

## *Project/Initiative*

## *Month 20YY*

## *Version X.XX*

*Company Information*

1. # **Document Revisions**

| Date | Version Number | Document Changes |
| ----- | ----- | ----- |
| 05/02/20xx | 0.1 | Initial Draft |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |

2. # **Approvals**

| Role | Name | Title | Signature | Date |
| ----- | ----- | ----- | ----- | ----- |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |

3. # **Introduction**

   1. ## **Project Summary**

      1. ### **Objectives**

*Reduce support workload by 40-50% by expanding the self-service system and minimize business losses from unexpected cancellations* 

2. ### **Background**

*Currently, all requests to cancel or change reservation dates are processed manually by the customer service, which creates a significant burden on the customer service and takes a long time due to the need to coordinate the changes with the hotel. In fact that the client base grows by 3-5% every month, accordingly, the time for processing one request by the support service increases, and the level of dissatisfied clients increases. The new functionality in the personal account should remove the operating routine and raise the level of user feedback.*

1. #### ***Business Drivers***

*The development of this feature is driven by several business needs:*

- *ensuring the automation of processes and their transparency without involving the support service*  
- *increasing the operational efficiency of the support service*   
- *minimization of business losses due to cancellation of reservations*


2. ## **Project Scope**

   

   

   1. ### **In Scope Functionality**

1. *Users can manage their bookings in the personal account*  
2. *The system sorts the user's reservation by status*  
3. *Users can cancel an existing booking in the personal account*  
4. *Users can substitute a room of the same type in an existing booking*   
5. *Users can change the dates of stay in an existing booking*   
6. *The system processes cancellation/change requests according to business rules*  
7. *The system automatically informs users and the hotel about changes in status or booking data be email*  
8. *The system automatically interacts with the payment system regarding transactions*

   

   2. ### **Out of Scope Functionality**

> > > * *User and hotel notification by SMS or push*  
> > > * *Adding new payment methods*  
> > > * *Substituting a room of a different type*   
> > > * *Modifying additional services in an existing booking*   
> > > * *Editing personal profile data in an existing booking*

  


  3. ## **System Perspective**

  *\[Provide a complete description of the factors that could prevent successful implementation or accelerate the projects, particularly factors related to legal and regulatory compliance, existing technical or operational limitations in the environment, and budget/resource constraints.\]*

     1. ### **Assumptions**

     2. ### **Constraints**

* 

  3. ### **Risks**

*   
* .

  4. ### **Issues**

* 


4. # **Business Process Overview**

   *\[Describe how the current process(es) work, including the interactions between systems and various business units. Include visual process flow diagrams to further illustrate the processes the new product will replace or enhance.*

   *Use case documentation and accompanying activity or process flow diagrams can be used to create the description(s) of the proposed or “To-Be” processes.\]*

   1. ## **Current Business Process (As-Is)**

At any point during or after deployment of web apps or web sites (internal or external) to support business activities, development/support teams may create and deploy widgets. 

1. CMS / database administrators for the employee portal use the CMS tool to create widgets. They can test widgets in the designated staging environment, then register them and deploy to production.  
2. Development teams may deploy widgets to development and testing environments set up for their development projects. They must check widget code into and out of the source code repository according to their projects’ development schedule.  
   ![][image1]

   2. ## **Proposed Business Process (To-Be)**

1. Technical Lead searches repository   
2. If widget is not found, user creates a new widget name record.  
3. WINS validates that all fields have been completed.  
4. WINS confirms that no similar widgets exist  
5. User confirms record to be created.  
   ![][image1]  
1. User searches repository to locate existing widget description.  
2. WINS displays record  
3. User selects Edit to open and modify record  
4. WINS validates all fields completed correctly  
5. User confirms changes.  
6. WINS confirms changes and updates Audit table.

   ![][image1]

5. # **Stakeholder Requirements**

1. *The user can cancel the reservation with one button without contacting the support service*  
2. *The business does not refund the customer if the cancellation occurred less than 24 hours before check-in*  
3. *The user can instantly change the reservation dates if there are available rooms*   
4. *The user must see the amount of the surcharge or refund before confirming the changes in the reservation*  
5. *The user can download the receipt in the system*  
6. *The user and the hotel should receive instant notification of changes in the booking*  
7. *The user can view his reservations in separate sections depending on the status "Active", "Completed", "Cancelled"*

   

The requirements in this document are prioritized as follows:

| Value | Rating | Description |
| ----- | ----- | ----- |
| 1 | Critical | This requirement is critical to the success of the project. The project will not be possible without this requirement. |
| 2 | High | This requirement is high priority, but the project can be implemented at a bare minimum without this requirement. |
| 3 | Medium | This requirement is somewhat important, as it provides some value but the project can proceed without it. |
| 4 | Low | This is a low priority requirement, or a “nice to have” feature, if time and cost allow it. |
| 5 | Future | This requirement is out of scope for this project, and has been included here for a possible future release. |

1. ## **Functional Requirements**

| Req\# | Priority | Description | Rationale | Use Case Reference | Impacted Stakeholders |
| ----- | ----- | ----- | ----- | ----- | ----- |
| **General / Base Functionality** |  |  |  |  |  |
| FR-G-001 | 1 | The system should provide the user with the opportunity to cancel an active reservation with one button in the personal account | Possibility to cancel the reservation without contacting the support service  |  | User |
| FR-G-002 | 1 | The system must check the tariff type before starting the cancellation. If the tariff is "Non-refundable", the system should block the cancellation and display a message about the impossibility of refund. | Minimizing losses  |  | Business owner  |
| FR-G-003 | 1 | The system should automatically calculate the amount to be refunded upon cancellation: Cancellation more than 24 hours before the start \- full refund Cancellation less than 24 hours before the start \- 100% penalty, no refund possible  | Minimizing losses |  | Business owner |
| FR-G-004 | 1 | The system should show the user the appropriate return conditions and request confirmation or cancellation of the action | The possibility to familiarize yourself with the conditions of cancellation before confirmation  |  | User |
| FR-G-005 | 1 | The system should send a notification to the hotel about the cancellation and change the status of the hotel on the specified dates, as well as transfer this reservation to the "cancelled" section  |  Hotel notification of changes  |  | Hotel |
| FR-G-006 | 2 | The system should send a notification to the user by email confirming the cancellation  | Confirmation of cancellation to the user  |  | User |
| FR-G-007 | 1 | The system should allow the user to change the reservation dates only if there are available rooms of the same type | Ability to change reservation dates without contacting support  |  | User |
| FR-G-008 | 1 | The system should display a message about the impossibility of changes if there are no free numbers  | Avoid business losses  |  | Business owner |
| FR-G-009 | 1 | The system should automatically calculate and display the amount to be refunded or surcharged to the user if the cost of the rooms is different, and request confirmation of the change  | The possibility to familiarize yourself with the conditions of cancellation before confirmation  |  | User |
| FR-G-010 | 1 | The system should generate a refund request if the number is cheaper  | Automatic refund  |  | User |
| FR-G-011 | 1 | The system should display an online surcharge form if the number is more expensive  | Possibility of online surcharge  |  | Business owner |
| FR-G-012 | 1 |  The system should change the dates in the reservation and reflect this in the personal account  | Display of current information  |  | Hotel, User |
| FR-G-013 | 1 | The system should send a message to the hotel about changes in the reservation  | Hotel notification of changes  |  | Hotel |
| FR-G-014 | 2 |  The system should send a notification to the user by email about changes in the reservation date  | Confirmation of booking changes to the user  |  | User |
| **Security Requirements** |  |  |  |  |  |
| FR-S-001 | 1 | Only an authorized user can cancel a reservation  |  |  |  |
| FR-S-002 | 1 | Only an authorized user can change the reservation dates  |  |  |  |
| **Reporting Requirements** |  |  |  |  |  |
| FR-R-001 | 2 | The system should offer the user to download a receipt for additional payment or send it to an e-mail  |  |  |  |
| **Usability Requirements** |  |  |  |  |  |
| FR-U-001 | 1 | The system should display reservations in the personal account according to their statuses in the sections "Active", "Completed", "Cancelled"  |  |  |  |
| **Audit Requirements** |  |  |  |  |  |
| FR-A-001 | 1 |  |  |  |  |

   2. ## **Non-Functional Requirements**

   *\[Include technical and operational requirements that are not specific to a function. This typically includes requirements such as processing time, concurrent users, availability, etc.\]*

| ID | Requirement |
| ----- | ----- |
| NFR-001 | The system must simultaneously process up to 1,000 applications |
| NFR-002 | The system must be available 99.8% of the time |
| NFR-003 | The calculation of the surcharge or refund should take no longer than 5 seconds |
| NFR-004 | Notification of cancellation or hotel change must be sent no longer than 3 seconds after confirmation of changes |
| NFR-005 | The user's payment data must be kept confidential  |

6. # **Appendices**

   1. ## **List of Acronyms**

   *\[If needed, create a list of acronyms used throughout the BRD document to aid in comprehension.\]*

   2. ## **Glossary of Terms**

   *\[If needed, identify and define any terms that may be unfamiliar to readers, including terms that are unique to the organization, the technology to be employed, or the standards in use.\]*

   3. ## **Related Documents**

   *\[Provide a list of documents or web pages, including links, which are referenced in the BRD.\]*

[image1]: <data:image/png;base64,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>