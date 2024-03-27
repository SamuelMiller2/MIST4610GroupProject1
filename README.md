# MIST4610 Group 6 Project 1

# Team Name:
47114 Group 6

# Team Members:
Samuel Miller

Sophia Scarangello 

Arika Chiluvuri <a href="https://github.com/Arikac03/MIST4610GroupProject1">Link</a>

Riley Eckstrom

Owen Donnelly

Michael Banks



# Problem Description
Goon's emergency healthcare clinic is a 24/7 facility that provides urgent medical care to patients with various health concerns. The clinic employs a skilled medical team who work in shifts to ensure continuous care. To efficiently manage the clinic's operations, our team has developed a comprehensive data model that captures the essential entities and their relationships. This includes patient information, visit details, diagnostic tests, equipment inventory, treatments, prescriptions, pharmacy inventory, billing, and payments. By implementing this data model, the clinic aims to streamline its operations, enhance patient care, optimize resource utilization, and improve overall efficiency. The database will serve as a centralized repository for storing and managing critical information, enabling the clinic staff to make informed decisions and provide the best possible care to their patients.

# Data Model
Data Model Description:

The data model for the emergency healthcare clinic consists of 11 main entities: Patients, Staff, Visits, DiagnosisTests, Equipment, Diagnosis, Treatment, Prescription, Pharmacy, Billing, and Payments. These entities are interconnected through various relationships, forming a comprehensive structure to manage the clinic's operations.
The Patients entity stores essential information about each patient, including their unique patientID, last name, first name, date of birth, gender, address, phone number, and insurance company. This entity serves as a central repository for patient data and is connected to other entities to track their visits, diagnoses, and billing information. The Staff entity represents the medical professionals working at the clinic. It contains attributes such as staffID, last name, first name, specialty, phone number, and job title. The Staff entity is associated with the Visits entity to record which staff member attends to each patient during their visit. The Visits entity captures information about each patient's visit to the clinic. It includes attributes like visitsID, timeIn, timeOut, reasonForVisit, patientID (foreign key referencing the Patients entity), and billingID (foreign key referencing the Billing entity). 

The Visits entity is connected to the Patients, Billing, and DiagnosisTests entities, allowing for a comprehensive record of each patient's clinic experience. The DiagnosisTests entity stores details about the diagnostic tests conducted during patient visits. It includes attributes such as equiptmentID (foreign key referencing the Equipment entity), visitsID (foreign key referencing the Visits entity), testDuration, testPerformed, and testDate. This entity is linked to the Visits and Equipment entities, enabling the tracking of test results and equipment usage. 
The Equipment entity keeps track of the medical equipment available in the clinic. It contains attributes like equiptmentID, itemName, quantityOwned, and purchaseDate. This entity is associated with the DiagnosisTests entity to record which equipment is used for each diagnostic test. The Diagnosis entity stores information about the diagnoses made for each patient visit. It includes attributes such as diagnosisID, diagnosis, diagnosisDescription, dateOfDiagnosis, and visitsID (foreign key referencing the Visits entity). The Diagnosis entity is connected to the Visits, Treatment, and Prescription entities, forming a link between the patient's diagnosis, prescribed treatment, and medication.

The Treatment entity captures details about the treatments provided to patients based on their diagnosis. It includes attributes like treatmentID, treatmentName, treatmentDescription, treatmentDate, treatmentLength, treatmentLocation, treatmentSupplies, and diagnosisID (foreign key referencing the Diagnosis entity). The Treatment entity is associated with the Diagnosis entity, allowing for a record of the specific treatments administered for each diagnosed condition. The Prescription entity stores information about the medications prescribed to patients. It includes attributes such as prescriptionID, medicationName, dosage, instructions, duration, diagnosisID (foreign key referencing the Diagnosis entity), and pharmacyID (foreign key referencing the Pharmacy entity). The Prescription entity is linked to the Diagnosis and Pharmacy entities, enabling the tracking of prescribed medications and their dispensing from the clinic's pharmacy. The Pharmacy entity represents the in-house pharmacy at the clinic. It contains attributes like pharmacyID, pharmacyName, pharmacyPhone, pharmacyHours, and pharmacyAddress. The Pharmacy entity is associated with the Prescription entity, facilitating the management of medication dispensing and inventory.
The Billing entity handles the financial aspects of patient visits. It includes attributes such as billingID, totalCharged, itemizedCharges, billingDate, dueDate, and paymentStatus. The Billing entity is connected to the Visits and Payments entities, allowing for the generation of bills based on the services provided during each visit and tracking the payment status. The Payments entity records the payment information for each bill. It includes attributes like paymentID, paymentStatus, paymentAmount, paymentMethod, paymentDate, and billingID (foreign key referencing the Billing entity). The Payments entity is associated with the Billing entity, enabling the tracking of payment details and status for each bill.


As far as relationships go, the Patients entity has a one-to-many relationship with the Visits entity, as a patient can have multiple visits to the clinic. The Staff entity has a many-to-many relationship with the Visits entity, as multiple staff members can attend to a patient during a visit, and a staff member can attend to multiple visits. The Visits entity has a one-to-many relationship with the DiagnosisTests entity, as multiple diagnostic tests can be conducted during a single visit. The Equipment entity has a one-to-many relationship with the DiagnosisTests entity, as a piece of equipment can be used in multiple diagnostic tests. The Visits entity has a one-to-many relationship with the Diagnosis entity, as a visit can result in multiple diagnoses. The Diagnosis entity has a one-to-many relationship with the Treatment entity, as a diagnosis can lead to multiple treatments. The Diagnosis entity has a one-to-many relationship with the Prescription entity, as a diagnosis can result in multiple prescribed medications. The Pharmacy entity has a one-to-many relationship with the Prescription entity, as the clinic's pharmacy can dispense multiple prescribed medications. The Visits entity has a one-to-one relationship with the Billing entity, as each visit generates a corresponding bill. The Billing entity has a one-to-many relationship with the Payments entity, as a bill can have multiple payments associated with it.

<img width="818" alt="image" src="https://github.com/SamuelMiller2/MIST4610GroupProject1/assets/150087690/756139c3-4a81-4cc8-a5e1-fddacc2ee280">

# Data Dictionary
<img width="681" alt="Screenshot 2024-03-26 at 6 39 05 PM" src="https://github.com/SamuelMiller2/MIST4610GroupProject1/assets/163004723/80c54b27-49d2-41a5-9132-a86579cc36eb">
<img width="691" alt="Screenshot 2024-03-26 at 6 39 27 PM" src="https://github.com/SamuelMiller2/MIST4610GroupProject1/assets/163004723/2cd7ce30-e672-4dc2-87cb-9cf3a665dc76">
<img width="679" alt="Screenshot 2024-03-26 at 6 39 43 PM" src="https://github.com/SamuelMiller2/MIST4610GroupProject1/assets/163004723/aea9df11-608d-4b44-8111-e10ec650d959">
<img width="687" alt="Screenshot 2024-03-26 at 6 40 02 PM" src="https://github.com/SamuelMiller2/MIST4610GroupProject1/assets/163004723/96b1be21-90b6-48a8-a8b2-629ea704deb6">
<img width="684" alt="Screenshot 2024-03-26 at 6 40 20 PM" src="https://github.com/SamuelMiller2/MIST4610GroupProject1/assets/163004723/564e76d5-7cc0-4b3b-93e8-449df09114de">
<img width="683" alt="Screenshot 2024-03-26 at 6 40 36 PM" src="https://github.com/SamuelMiller2/MIST4610GroupProject1/assets/163004723/3e36dafc-3008-4c6e-bea5-ddb0dcf6e1a5">
<img width="690" alt="Screenshot 2024-03-26 at 6 41 04 PM" src="https://github.com/SamuelMiller2/MIST4610GroupProject1/assets/163004723/c8c68966-1b4c-4c45-838f-54a731bc68a3">
<img width="696" alt="Screenshot 2024-03-26 at 6 41 17 PM" src="https://github.com/SamuelMiller2/MIST4610GroupProject1/assets/163004723/9ac5639e-56b2-4bf4-afe2-cbc088cf944c">
<img width="689" alt="Screenshot 2024-03-26 at 6 41 31 PM" src="https://github.com/SamuelMiller2/MIST4610GroupProject1/assets/163004723/cfce7023-6756-43ca-9dfe-89f2795e82ea">
<img width="687" alt="Screenshot 2024-03-26 at 6 41 42 PM" src="https://github.com/SamuelMiller2/MIST4610GroupProject1/assets/163004723/c8d9e571-35c6-4a86-a64f-cf993bb50260">
<img width="686" alt="Screenshot 2024-03-26 at 6 41 54 PM" src="https://github.com/SamuelMiller2/MIST4610GroupProject1/assets/163004723/cee4b9e8-5777-485d-bbda-9801d2d0d10f">
<img width="685" alt="Screenshot 2024-03-26 at 6 42 08 PM" src="https://github.com/SamuelMiller2/MIST4610GroupProject1/assets/163004723/fd18d128-c1ec-4200-821b-d565b03f2c9d">


# Queries
<img width="488" alt="image" src="https://github.com/SamuelMiller2/MIST4610GroupProject1/assets/163002732/af3ae506-840a-462a-8413-b023f901070c">

1. List the patient's first and last name combined for patients whose total bill amount is greater than the average bill amount of the insurance company they belong to.

Justification: This query helps the urgent care manager identify patients with higher than average bills for their insurance company. It can be used to analyze billing patterns, negotiate rates with insurance providers, and identify potential billing issues.
<img width="877" alt="Screenshot 2024-03-26 at 6 28 48 PM" src="https://github.com/SamuelMiller2/MIST4610GroupProject1/assets/131375287/c92520bb-fc1c-497c-ac48-4569277c81f7">

2. List the medical staff's first name and specialty who treat patients that are female and don't use State Farm insurance.

Justification: This query helps the manager identify the medical staff and their specialties that cater to a specific demographic of patients. It can be used for resource allocation, staff training, and understanding patient preferences.
<img width="877" alt="Screenshot 2024-03-26 at 6 29 32 PM" src="https://github.com/SamuelMiller2/MIST4610GroupProject1/assets/131375287/386917b6-18b7-4485-8d3b-ccba7fd045aa">

3. List the patient's visit time, medication name, duration, and pharmacy name for patients who have 2 or more appointments. Group by patientID.

Justification: This query helps the manager identify patients with multiple appointments and their associated medications and pharmacies. By grouping the results by patient instead of visit time, we can still monitor medication adherence, pharmacy partnerships, and patient follow-up for patients with frequent visits. This information can be used to optimize patient care, ensure medication compliance, and strengthen relationships with pharmacies.
<img width="877" alt="Screenshot 2024-03-26 at 6 32 12 PM" src="https://github.com/SamuelMiller2/MIST4610GroupProject1/assets/131375287/f8029ee5-a32f-4dc8-8d1d-23fc1108c19c">

4. Print out the patient's full name and the number of payments they have made that were greater than $5,000 dollars.

Justification: This query helps the manager identify patients who have made payments higher than five thousand dollars. It can be used to analyze payment patterns, identify potential billing errors, and recognize patients who may be struggling financially.
<img width="877" alt="Screenshot 2024-03-26 at 6 32 30 PM" src="https://github.com/SamuelMiller2/MIST4610GroupProject1/assets/131375287/b3e9dbd6-e75f-4d7c-a646-b6a6c893ca88">

5. Write a query to list the number of patients each specialty has seen.

Justification: This query helps the manager assess the workload of each specialty group and identify any potential staffing issues. It can be used for performance evaluations, resource allocation, and staff training.
<img width="877" alt="Screenshot 2024-03-26 at 6 32 47 PM" src="https://github.com/SamuelMiller2/MIST4610GroupProject1/assets/131375287/6d356844-47c4-49cc-8c31-478d877a7495">

6. Write a query to list the name of the pharmacy, the pharmacy phone number, and count the number of patients each pharmacy is responsible for if the patient's prescription is Xanax. List the pharmacies in alphabetical order.

Justification: This query helps the manager identify pharmacies that dispense a specific medication and the number of patients they serve. It can be used to monitor medication usage, pharmacy partnerships, and patient care.
<img width="877" alt="Screenshot 2024-03-26 at 6 33 13 PM" src="https://github.com/SamuelMiller2/MIST4610GroupProject1/assets/131375287/e7d510aa-a1d4-40c2-b98d-f139c3103d57">

7. Find the full patient names and the reason for visit for patients who had a visit but were not prescribed anything. Order the patients by their age, youngest to oldest.

Justification: This query helps the manager identify patients who visited the urgent care but did not receive any prescriptions. It can be used to analyze patient care, identify potential missed diagnoses, and improve patient outcomes.
<img width="877" alt="Screenshot 2024-03-26 at 6 33 30 PM" src="https://github.com/SamuelMiller2/MIST4610GroupProject1/assets/131375287/960c16f5-3a98-4b2c-b641-b16afe62eae3">

8. Write a query that identifies patients with unpaid or pending bills and their total bill amount.

Justification: This helps the manager track the payment status of patient bills and identify any outstanding balances. They can be used for financial reporting, collections, and patient communication.
<img width="877" alt="Screenshot 2024-03-26 at 6 33 42 PM" src="https://github.com/SamuelMiller2/MIST4610GroupProject1/assets/131375287/54d01a80-9a01-4cfb-bb19-27ceb191b405">

9. Write a query that lists the most commonly diagnosed conditions and their frequencies from greate
st to least.

Justification: This query helps the manager identify the most common conditions treated at the urgent care. It can be used for resource allocation, staff training, and patient education.
<img width="877" alt="Screenshot 2024-03-26 at 6 35 01 PM" src="https://github.com/SamuelMiller2/MIST4610GroupProject1/assets/131375287/042021ce-e1e4-4de6-91fb-ad2d236d7ffe">

10. Write a query that identifies the staff members and how many prescriptions they have written. Include their job title and specialty.
Justification: This query helps the urgent care manager identify the staff members who are the most active in prescribing medications. It can be used to analyze prescribing patterns, identify potential over-prescribing, and ensure that staff members are practicing within their scope of practice. By including the job title and specialty, the manager can also assess if the prescribing patterns align with the staff member's role and expertise.
<img width="877" alt="Screenshot 2024-03-26 at 6 39 27 PM" src="https://github.com/SamuelMiller2/MIST4610GroupProject1/assets/131375287/0d651e91-dc3c-4bd6-8351-f27c6196719b">


# Database Information

Name of the database: ns_Sp24_47114_Group6

Additional information: Each query listed above is marked in the database using stored procedures which can be called using the following format: CALL TP_Q1();
