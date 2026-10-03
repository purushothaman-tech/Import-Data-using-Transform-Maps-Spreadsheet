# Import Data Using Transform Maps – Spreadsheet

**Team ID:** SWTID-2026-8426  
**Platform:** ServiceNow  
**Project:** Import Data using Transform Maps (Spreadsheet)

---

## 📌 Project Overview

The **Import Data Using Transform Maps – Spreadsheet** project is a ServiceNow-based data import and management solution designed to efficiently migrate structured employee information from an external spreadsheet into ServiceNow.

The project demonstrates how employee data received in **Excel format** can be loaded into ServiceNow using **Import Sets and Transform Maps**. The spreadsheet data is first stored in an Import Set Table, which acts as a staging area. A Transform Map then maps the source fields to the corresponding fields in the target **Employee Test** table.

The project is further enhanced with **Coalesce** to prevent duplicate records during repeated imports, along with **Reports and an Employee Analytics Dashboard** for analyzing employee data.

---

## 🎯 Problem Statement

Employee information may be received from external sources in spreadsheet format and needs to be imported into ServiceNow accurately.

A manual data entry and migration process can result in:

* Increased manual effort
* Data entry errors
* Incorrect field mapping
* Duplicate employee records
* Difficulty handling repeated imports
* Limited visibility into imported employee data

The project addresses these requirements by using **ServiceNow Import Sets and Transform Maps** to create a structured and repeatable employee data import process.

---

## 💡 Proposed Solution

The solution uses a spreadsheet containing employee information such as:

* **Employee ID**
* **Employee Name**
* **Email**
* **Department**
* **Location**

The spreadsheet is loaded into an **Import Set Table** and then transformed into the **Employee Test** target table using a Transform Map.

The Transform Map maps the source fields to the appropriate target fields. **Coalesce** is enabled to identify existing employee records during subsequent imports and help prevent duplicate records.

---

## ⚙️ Import and Transformation Process

| Source Field | Target Field |
|--------------|--------------|
| Employee ID | Employee ID |
| Employee Name | Employee Name |
| Email | Email |
| Department | Department |
| Location | Location |

### Coalesce

The **Employee ID** field is configured for Coalesce to identify existing employee records.

When employee data is imported again:

* New Employee IDs are inserted as new records.
* Existing Employee IDs can be updated with changed information.
* Repeated identical records can be ignored.
* Duplicate employee records are avoided.

---

## 🧪 Testing

The project is tested using different employee spreadsheet import scenarios to verify data insertion, updating, duplicate prevention, and transformation results.

| Test Case | Input / Scenario | Expected Result |
|-----------|------------------|-----------------|
| TC01 | Import the initial employee spreadsheet | Employee records are successfully inserted into the Employee Test table |
| TC02 | Import spreadsheet containing new Employee IDs | New employee records are inserted |
| TC03 | Import an existing Employee ID with a changed Name | Existing employee record is updated |
| TC04 | Import an existing Employee ID with a changed Email | Existing employee record is updated |
| TC05 | Import the same spreadsheet again | Duplicate records are not created |
| TC06 | Check Transform History after import | Inserted, updated, and ignored records are displayed correctly |
| TC07 | Open Employee Test table after transformation | Imported and updated employee records are displayed correctly |
| TC08 | Verify Employees by Department report | Employee records are grouped correctly by department |
| TC09 | Verify Employees by Location report | Employee records are grouped correctly by location |
| TC10 | Verify Employee List Report | Employee ID, Name, Email, Department, and Location are displayed correctly |
| TC11 | Verify Employee Analytics Dashboard | All configured reports are displayed on the dashboard |

### Testing Outcome

The testing confirms that the employee spreadsheet data can be successfully imported into ServiceNow using Import Sets and Transform Maps. New records are inserted, existing records are updated using the configured Coalesce field, and repeated identical imports do not create unnecessary duplicate records.

The reports and Employee Analytics Dashboard are also verified to ensure that the imported employee data is displayed correctly.

---

## 👥 Team

**Team ID:** SWTID-2026-8426

**Project:** Import Data using Transform Maps (Spreadsheet)

**Platform:** ServiceNow
