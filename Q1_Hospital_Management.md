# Question 1 — Hospital Management System (Healthcare Industry)

## Scenario

A private hospital network is expanding its operations and needs a robust database system to manage everything from staff to patient care. You have been hired as a database designer to model this system.

The hospital is organized into several **departments**, such as Cardiology, Neurology, Pediatrics, and Orthopedics. Each department has a unique name, a physical location within the hospital building, and a dedicated head of department. A department can employ many doctors, but each doctor is assigned to exactly one department at any given time.

Each **doctor** working at the hospital has a full name, a medical license number, a specialization (e.g., Surgeon, General Practitioner), a contact phone number, and an email address. Doctors work within their assigned department and are responsible for treating patients.

**Patients** register with the hospital before receiving any treatment. A patient's record includes their full name, date of birth, gender, national identity number, home address, and an emergency contact number. A patient may visit the hospital multiple times over their lifetime.

Every time a patient comes to the hospital, a **visit record** is created. This record captures the date and time of the visit, the patient's presenting symptoms, the diagnosis made by the attending doctor, and the prescribed treatment plan. A single visit is attended by one doctor, but over different visits, a patient may be seen by different doctors. Similarly, a doctor handles many patient visits over their career at the hospital.

During a visit, a doctor may prescribe one or more **medicines** to the patient. The hospital maintains a master list of all available medicines, each with a unique medicine code, a generic name, a brand name, the form it comes in (e.g., tablet, syrup, injection), and its unit price. A single prescription issued during a visit can include multiple medicines, and the same medicine can be prescribed across many different visits. For each medicine included in a prescription, the dosage instructions and the quantity to be dispensed must also be captured.

The hospital has a number of **rooms** available for patients who require admission. Each room has a room number, a room type (e.g., General Ward, ICU, Private Room), a floor number, and a daily charge rate. When a patient is admitted, they are assigned to one specific room. The same room can be used by different patients at different times, but only one patient occupies a room at a time. The admission record must store the date the patient was admitted and the date they were discharged.

---

## Your Task

Draw a complete **Entity-Relationship (ER) Diagram** for the Hospital Management System described above.

Your diagram must:

1. Identify and clearly label all **entities** in the system.
1.Department
2.Doctor
3.Patient
4.Visit
5.Medicine
6.Prescription 
7.Room
8.Admission

2. List the **attributes** for each entity — underline or mark the **primary key** attribute.

1.Department
Department_ID (PK)
Department_Name
Location
Head_Of_Department

2.Doctor
Doctor_ID (PK)
Full_Name
Medical_License_No
Specialization
Phone
Email

3.Patient
Patient_ID (PK)
Full_Name
DOB
Gender
NIC
Address
Emergency_Contact_No

4.Visit
Visit_ID (PK)
Visit_Date_Time
Symptoms
Diagnosis
Treatment_Plan

5.Medicine
Medicine_Code (PK)
Generic_Name
Brand_Name
Form
Unit_Price


6..Room
Room_No (PK)
Room_Type
Floor_No
Daily_Charge_Rate

8.Admission
Admission_ID (PK)
Admission_Date
Discharge_Date

3. Identify all **relationships** between entities and give each relationship a meaningful name.

Department → Employs → Doctor

Patient → Has → Visit

Doctor → Attends → Visit

Visit → Prescribes → Medicine

Patient → Gets_Admitted → Admission

Room → Assigned_To → Admission


4. Specify the correct **cardinality** (1:1, 1:N, or M:N) and **participation constraints** (total or partial) for every relationship.
Relationship	                        Cardinality             	Participation Constraint
Department — Employs — Doctor	            1 : N	            Doctor = Total, Department = Partial
Patient — Has — Visit	                    1 : N	            Visit = Total, Patient = Partial
Doctor — Attends — Visit	                1 : N	            Visit = Total, Doctor = Partial
Visit — Prescribes — Medicine	            M : N	            Visit = Partial, Medicine = Partial
Patient — Gets_Admitted — Admission	        1 : N	            Admission = Total, Patient = Partial
Room — Assigned_To — Admission	            1 : N	            Admission = Total, Room = Partial
Visit — Prescription — Medicine	            1 : N              	Prescription = Total

5. Identify any **weak entities** and their identifying relationships.

Prescription is the weak entity.
Visit → Prescribes → Medicine

6. For every **M:N relationship**, identify and include the **relationship attributes** that belong to the association, not to either individual entity.
Visit ↔ Prescribes ↔ Medicine

M : N

Relationship Attributes:
Dosage_Instructions
Quantity

//ERd link
https://drive.google.com/file/d/1vnGBhBmYEflghYZ6xRWPCsmET_YZvFsn/view?usp=sharing
---

## Marking Criteria

| Criteria | Marks |
|----------|-------|
| Correct entities identified | 10 |
| Correct attributes with primary keys | 10 |
| Correct relationships & cardinality | 15 |
| Weak entities / relationship attributes | 10 |
| Diagram clarity and notation | 5 |
| **Total** | **50** |

