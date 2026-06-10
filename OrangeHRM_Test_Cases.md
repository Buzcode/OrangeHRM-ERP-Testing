# OrangeHRM Detailed Test Cases (32 Cases)

This document contains the step-by-step test cases executed against the OrangeHRM system requirements.

---

### TC_OHRM_001
*   **Description:** Verify successful login with valid Admin credentials.
*   **Pre-conditions:** Browser is open; user is on the OrangeHRM login page.
*   **Test Data:** Username: `Admin`, Password: `admin123`
*   **Steps:**
    1. Enter `Admin` in the Username field.
    2. Enter `admin123` in the Password field.
    3. Click the "Login" button.
*   **Expected Result:** User is successfully logged in and redirected to the `/dashboard/index` page.
*   **Actual Result:** User was successfully logged in and redirected to the `/dashboard/index` page.
*   **Status:** Pass

---

### TC_OHRM_002
*   **Description:** Verify login failure when entering an invalid username with a valid password.
*   **Pre-conditions:** Browser is open; user is on the OrangeHRM login page.
*   **Test Data:** Username: `invalidUser`, Password: `admin123`
*   **Steps:**
    1. Enter `invalidUser` in the Username field.
    2. Enter `admin123` in the Password field.
    3. Click the "Login" button.
*   **Expected Result:** User is blocked from logging in, and the validation error message "Invalid credentials" is displayed.
*   **Actual Result:** User was blocked from logging in, and the message "Invalid credentials" was displayed.
*   **Status:** Pass

---

### TC_OHRM_003
*   **Description:** Verify login failure when entering a valid username with an invalid password.
*   **Pre-conditions:** Browser is open; user is on the OrangeHRM login page.
*   **Test Data:** Username: `Admin`, Password: `wrongPassword`
*   **Steps:**
    1. Enter `Admin` in the Username field.
    2. Enter `wrongPassword` in the Password field.
    3. Click the "Login" button.
*   **Expected Result:** User is blocked from logging in, and the validation error message "Invalid credentials" is displayed.
*   **Actual Result:** User was blocked from logging in, and the message "Invalid credentials" was displayed.
*   **Status:** Pass

---

### TC_OHRM_004
*   **Description:** Verify login failure when leaving the password field blank.
*   **Pre-conditions:** Browser is open; user is on the OrangeHRM login page.
*   **Test Data:** Username: `Admin`, Password: `[Blank]`
*   **Steps:**
    1. Enter `Admin` in the Username field.
    2. Leave the Password field completely empty.
    3. Click the "Login" button.
*   **Expected Result:** User is blocked from logging in, and a red validation message "Required" is displayed below the password field.
*   **Actual Result:** User was blocked from logging in, and the message "Required" was displayed below the password field.
*   **Status:** Pass

---

### TC_OHRM_005
*   **Description:** Verify that attempting to access the dashboard URL directly without an active session redirects back to the login page (Session Security).
*   **Pre-conditions:** Browser is open in a new Incognito/Private window (ensuring no session cookie is stored).
*   **Test Steps:**
    1. Paste this URL directly into the browser address bar: `https://opensource-demo.orangehrmlive.com/web/index.php/dashboard/index`
    2. Press the Enter key.
*   **Expected Result:** Access is blocked; the browser is automatically redirected to the login page (`/web/index.php/auth/login`).
*   **Actual Result:** Access was blocked, and the browser was successfully redirected back to the login page.
*   **Status:** Pass

---

### TC_OHRM_006
*   **Description:** Verify redirection to the reset password feature using the "Forgot your password?" link.
*   **Pre-conditions:** Browser is open; user is on the OrangeHRM login page.
*   **Test Steps:**
    1. Click the "Forgot your password?" link located on the login panel.
*   **Expected Result:** User is redirected to the "Reset Password" page (`/web/index.php/auth/requestPasswordResetCode`).
*   **Actual Result:** User was successfully redirected to the "Reset Password" page.
*   **Status:** Pass

---

### TC_OHRM_007
*   **Description:** Verify that the system displays matching records in the employee table when searching by a valid Employee Name.
*   **Pre-conditions:** Browser is open; user is logged in and is on the OrangeHRM PIM Employee List page.
*   **Test Steps:**
    1. Click on the 'Employee Name' search input field.
    2. Type `Abhishek` in the field.
    3. Select the matching employee profile from the dynamic auto-suggest hints list.
    4. Click the 'Search' button.
*   **Test Data:** Employee Name = `Abhishek`
*   **Expected Result:** The system displays matching name suggestions while typing. Once 'Search' is clicked, the employee table filters to display records matching "Abhishek."
*   **Actual Result:** The employee list table successfully filtered and displayed only the records matching the name 'Abhishek'.
*   **Status:** Pass

---

### TC_OHRM_008
*   **Description:** Verify that the system displays matching records in the employee table when searching by a valid Employee ID.
*   **Pre-conditions:** Browser is open; user is logged in and is on the OrangeHRM PIM Employee List page.
*   **Test Steps:**
    1. Click on the 'Employee Id' search input field.
    2. Enter a valid ID in the field.
    3. Click the 'Search' button.
*   **Test Data:** Employee ID = `0024`
*   **Expected Result:** The employee list table filters and displays only the specific record matching Employee ID 0024.
*   **Actual Result:** The employee list table successfully filtered and displayed only the record matching the specified Employee ID 0024.
*   **Status:** Pass

---

### TC_OHRM_009
*   **Description:** Verify that the 'Reset' button clears all active search filters and restores the default employee list in the PIM module.
*   **Pre-conditions:** User is logged in and is on the PIM Employee List page.
*   **Test Steps:**
    1. Enter a valid name in the 'Employee Name' field.
    2. Enter a valid ID in the 'Employee Id' field.
    3. Click the "Reset" button (located next to the Search button).
*   **Test Data:** Employee Name = `Abhishek`, Employee ID = `0024`
*   **Expected Result:** All entered search values are cleared, input fields return to empty, and the table below restores the default, unfiltered employee list.
*   **Actual Result:** Input fields were cleared and the default employee list was successfully restored on clicking Reset.
*   **Status:** Pass

---

### TC_OHRM_010
*   **Description:** Verify error handling when attempting to upload an invalid file type as an employee profile picture.
*   **Pre-conditions:** User is logged in and is on the "Add Employee" page in the PIM module.
*   **Test Steps:**
    1. Click on the profile picture upload button.
    2. Attempt to upload a non-image file (e.g., a `.pdf` or `.txt` file).
*   **Test Data:** A sample file named `test_document.pdf`.
*   **Expected Result:** The system should reject the file, display an error message (e.g., "File type not allowed"), and prevent the upload.
*   **Actual Result:** The system rejected the file, displayed an error message saying "File type not allowed", and prevented the upload. (Misleading error message).
*   **Status:** Pass

---

### TC_OHRM_011
*   **Description:** Verify error handling when attempting to upload a profile picture that is larger than 1MB.
*   **Pre-conditions:** User is logged in and is on the "Add Employee" page in the PIM module.
*   **Test Steps:**
    1. Click on the profile picture upload button.
    2. Attempt to upload an image format (`.png` or `.jpg`) with a file size larger than 1MB.
*   **Test Data:** An image named `large_image.png` (Size: 1.5MB).
*   **Expected Result:** The system should reject the file and display an error message: "Attachment size exceeded".
*   **Actual Result:** The system rejected the file, displayed the error message "Attachment size exceeded", and prevented the upload.
*   **Status:** Pass

---

### TC_OHRM_012
*   **Description:** Verify that enabling the "Create Login Details" toggle expands the form to display login fields.
*   **Pre-conditions:** User is logged in and is on the "Add Employee" page in the PIM module.
*   **Test Steps:**
    1. Fill in the First Name and Last Name fields.
    2. Locate the "Create Login Details" toggle/switch.
    3. Click the toggle to enable it.
*   **Expected Result:** The form dynamically expands to display fields for Username, Password, Confirm Password, and Status.
*   **Actual Result:** The form dynamically expanded and displayed fields for Username, Password, Confirm Password, and Status.
*   **Status:** Pass

---

### TC_OHRM_013
*   **Description:** Verify error handling when attempting to save a new employee with the mandatory "First Name" field left blank.
*   **Pre-conditions:** User is logged in and is on the "Add Employee" page in the PIM module.
*   **Test Steps:**
    1. Leave the First Name field completely empty.
    2. Enter a valid name in the Last Name field.
    3. Click the Save button.
*   **Expected Result:** The system blocks saving and displays a red "Required" error message below the First Name field.
*   **Actual Result:** The system blocked saving and displayed a red "Required" error message below the First Name field.
*   **Status:** Pass

---

### TC_OHRM_014
*   **Description:** Verify error handling when attempting to save a new employee with the mandatory "Last Name" field left blank.
*   **Pre-conditions:** User is logged in and is on the "Add Employee" page in the PIM module.
*   **Test Steps:**
    1. Enter a valid name in the First Name field.
    2. Leave the Last Name field completely empty.
    3. Click the Save button.
*   **Expected Result:** The system blocks saving and displays a red "Required" error message below the Last Name field.
*   **Actual Result:** The system blocked saving and displayed a red "Required" error message below the Last Name field.
*   **Status:** Pass

---

### TC_OHRM_015
*   **Description:** Verify that the report search bar auto-suggests existing reports as the user types.
*   **Pre-conditions:** User is logged in and is on the "Reports" page in the PIM module.
*   **Test Steps:**
    1. Click on the search bar.
    2. Type the first few letters of an existing report (e.g., "PIM").
*   **Expected Result:** A dropdown list appears dynamically below the search bar displaying matching reports containing the typed keyword.
*   **Actual Result:** A dropdown list appeared dynamically below the search bar and displayed matching reports containing the keyword typed.
*   **Status:** Pass

---

### TC_OHRM_016
*   **Description:** Verify that clicking the "Add" button in the Reports section opens the Define Report form.
*   **Pre-conditions:** User is logged in and is on the "Reports" page in the PIM module.
*   **Test Steps:**
    1. Locate the "Add" button on the top right.
    2. Click the "Add" button.
*   **Expected Result:** The system redirects the user to the "Define Report" page with input fields for Report Name, Selection Criteria, and Display Fields.
*   **Actual Result:** The system redirected the user to the "Define Report" page with input fields for Report Name, Selection Criteria, and Display Fields.
*   **Status:** Pass

---

### TC_OHRM_017
*   **Description:** Verify error handling when attempting to add a new system user with a username that already exists in the system.
*   **Pre-conditions:** User is logged in, is on the "Admin -> User Management -> Users" page, and has clicked "Add".
*   **Test Steps:**
    1. Select a User Role (e.g., Admin or ESS).
    2. Enter an existing system employee's name in the Employee Name field.
    3. Enter an existing, registered username in the Username field (e.g., Admin).
    4. Fill out the password fields and click Save.
*   **Test Data:** Username: `Admin`
*   **Expected Result:** The system blocks the save action and displays a validation error message "Already exists" directly below the Username field.
*   **Actual Result:** The system blocked the save action and displayed a validation error message "Already exists" directly below the Username field.
*   **Status:** Pass

---

### TC_OHRM_018
*   **Description:** Verify that the system user search list filters correctly when searching by User Role.
*   **Pre-conditions:** User is logged in and is on the "Admin -> User Management -> Users" page.
*   **Test Steps:**
    1. Click on the "User Role" dropdown.
    2. Select Admin (or ESS).
    3. Click the Search button.
*   **Expected Result:** The system filters the search results table to display only users who have the selected role.
*   **Actual Result:** The system filtered the search results table to display only users who have the selected role.
*   **Status:** Pass

---

### TC_OHRM_019
*   **Description:** Verify that a newly created job title is successfully saved and appears in the Job Titles list.
*   **Pre-conditions:** User is logged in, is on the "Admin -> Job -> Job Titles" page, and has clicked the "Add" button.
*   **Test Steps:**
    1. Enter a unique title in the "Job Title" field.
    2. Enter a brief description in the "Job Description" field.
    3. Click the Save button.
*   **Test Data:** Job Title: `QA Lead Specialist`
*   **Expected Result:** The job title is saved, and the user is redirected to the Job Titles list where "QA Lead Specialist" is displayed in alphabetical order.
*   **Actual Result:** The job title is saved, and the user is redirected to the Job Titles list where "QA Lead Specialist" is displayed in alphabetical order.
*   **Status:** Pass

---

### TC_OHRM_020
*   **Description:** Verify system behavior and deletion confirmation popup when selecting multiple employees from the list and clicking the 'Delete Selected' button.
*   **Pre-conditions:** User is logged in and is on the PIM Employee List page.
*   **Test Steps:**
    1. Check the selection boxes next to at least two employees in the list.
    2. Click the "Delete Selected" button.
*   **Expected Result:** A confirmation popup appears asking the user to confirm the deletion ("Are you sure?"). The actual deletion should only happen after confirming "Yes, Delete" on the popup.
*   **Actual Result:** A confirmation popup appeared asking the user to confirm the deletion ("Are you sure?"). The actual deletion should only happen after confirming "Yes, Delete" on the popup.
*   **Status:** Pass

---

### TC_OHRM_021
*   **Description:** Verify that edits made to an employee's profile (e.g., Blood Type or License Number) on the 'Personal Details' page are successfully saved.
*   **Pre-conditions:** User is logged in, has opened an existing employee's profile, and is on the "Personal Details" tab.
*   **Test Steps:**
    1. Locate the "Driver's License Number" field and enter a new value.
    2. Locate the "Blood Type" dropdown and select a type.
    3. Click the "Save" button for the respective section.
*   **Test Data:** License Number: `DL-998877`, Blood Type: `O+`
*   **Expected Result:** The system displays a success toast notification "Successfully Updated", and the saved values persist when the page is refreshed.
*   **Actual Result:** The system displayed a success toast notification "Successfully Updated", and the saved values persist when the page is refreshed.
*   **Status:** Pass

---

### TC_OHRM_022
*   **Description:** Verify that a user can successfully upload an attachment (like a contract or resume) to an employee's profile.
*   **Pre-conditions:** User is logged in, has opened an existing employee's profile, and is on the "Personal Details" tab.
*   **Test Steps:**
    1. Scroll down to the "Attachments" section.
    2. Click the "Add" button in the Attachments section.
    3. Click "Browse" and select a valid PDF/Word file.
    4. Click the Save button.
*   **Test Data:** A sample file named `Employee_Contract.pdf`.
*   **Expected Result:** The file is uploaded, a success message is displayed, and the file appears listed in the Attachments grid.
*   **Actual Result:** The file is uploaded, a success message is displayed, and the file appears listed in the Attachments grid.
*   **Status:** Pass

---

### TC_OHRM_023
*   **Description:** Verify that changes made to an employee's contact details (such as email or telephone) are successfully saved.
*   **Pre-conditions:** User is logged in, has opened an existing employee's profile, and is on the "Contact Details" tab.
*   **Test Steps:**
    1. Locate the "Mobile" field and enter a phone number.
    2. Locate the "Work Email" field and enter a valid email address.
    3. Click the Save button.
*   **Test Data:** Mobile: `01712345678`, Email: `testemployee@orangehrm.com`
*   **Expected Result:** The contact details are updated, a success message is displayed, and the changes are saved.
*   **Actual Result:** The contact details are updated, a success message is displayed, and the changes are saved.
*   **Status:** Pass

---

### TC_OHRM_024
*   **Description:** Verify that a user can add emergency contact details for an employee.
*   **Pre-conditions:** User is logged in, has opened an existing employee's profile, and is on the "Emergency Contacts" tab.
*   **Test Steps:**
    1. Click the "Add" button.
    2. Enter a Name, Relationship, and Mobile number.
    3. Click the Save button.
*   **Test Data:** Name: `Robert Johnson`, Relationship: `Brother`, Mobile: `01812345678`
*   **Expected Result:** The emergency contact is saved, and Robert Johnson is added to the Emergency Contacts list.
*   **Actual Result:** The emergency contact is saved, and Robert Johnson is added to the Emergency Contacts list.
*   **Status:** Pass

---

### TC_OHRM_025
*   **Description:** Verify that a system user can be successfully deleted from the Admin User list.
*   **Pre-conditions:** User is logged in and is on the "Admin -> User Management -> Users" page.
*   **Test Steps:**
    1. Identify a non-admin system user to delete.
    2. Click the trash bin icon (Delete button) next to their record.
    3. Confirm the deletion on the popup modal.
*   **Expected Result:** The system user is deleted, a success notification appears, and their username no longer appears in the list.
*   **Actual Result:** The system user is deleted, a success notification appears, and their username no longer appears in the list.
*   **Status:** Pass

---

### TC_OHRM_026
*   **Description:** Verify that the system user search list filters correctly when searching by status (Enabled/Disabled).
*   **Pre-conditions:** User is logged in and is on the "Admin -> User Management -> Users" page.
*   **Test Steps:**
    1. Click on the "Status" dropdown.
    2. Select Disabled (or Enabled).
    3. Click the Search button.
*   **Expected Result:** The search results table updates to display only users whose status matches the selected filter.
*   **Actual Result:** The search results table updates to display only users whose status matches the selected filter.
*   **Status:** Pass

---

### TC_OHRM_027
*   **Description:** Verify that the Employee List can be sorted by Employee ID in ascending and descending order.
*   **Pre-conditions:** User is logged in and is on the PIM Employee List page.
*   **Test Steps:**
    1. Locate the "Id" column header in the employee table.
    2. Click the "Id" column header once to sort.
    3. Click the "Id" column header a second time.
*   **Expected Result:** The table sorts the records numerically by employee ID in ascending order on the first click, and descending order on the second click.
*   **Actual Result:** The table sorts the records numerically by employee ID in ascending order on the first click, and descending order on the second click.
*   **Status:** Pass

---

### TC_OHRM_028
*   **Description:** Verify that a standard .jpg image under 1MB uploads successfully as a profile picture.
*   **Pre-conditions:** User is logged in and is on the "Add Employee" page in the PIM module.
*   **Test Steps:**
    1. Click on the profile picture upload icon.
    2. Choose a valid .jpg image file.
    3. Click Open/Save.
*   **Test Data:** A standard image named `profile_photo.jpg` (Size: 200KB).
*   **Expected Result:** The image uploads successfully, displaying a thumbnail preview of the profile picture on the form.
*   **Actual Result:** The image uploaded successfully, displaying a thumbnail preview of the profile picture on the form.
*   **Status:** Pass

---

### TC_OHRM_029
*   **Description:** Verify that the top navigation bar profile dropdown expands and collapses correctly.
*   **Pre-conditions:** User is logged in and is on any dashboard page.
*   **Test Steps:**
    1. Click on the profile picture/name in the top-right corner.
    2. Observe the menu options.
    3. Click on the profile picture/name a second time (or click outside the menu).
*   **Expected Result:** The dropdown menu expands on the first click to display links (like About, Support, Change Password, Logout) and collapses on the second click.
*   **Actual Result:** The dropdown menu expands on the first click to display links, but does not collapse on the second click (sticky menu).
*   **Status:** Fail

---

### TC_OHRM_030
*   **Description:** Verify that logging out successfully terminates the active user session and redirects to the login page.
*   **Pre-conditions:** User is logged in and is on any dashboard page.
*   **Test Steps:**
    1. Click on the profile picture/name in the top-right corner.
    2. Click the "Logout" link.
*   **Expected Result:** The user is logged out, the active session is terminated, and the browser is redirected to the OrangeHRM login page.
*   **Actual Result:** The user was logged out, the session was terminated, and the browser was redirected to the login page.
*   **Status:** Pass

---

### TC_OHRM_031
*   **Description:** Verify that the "Name" field in the Assigned Dependents form rejects special characters and numbers.
*   **Pre-conditions:** User is logged in as Admin and is on the PIM Dependents page of an employee profile.
*   **Test Steps:**
    1. Click the "+ Add" button under "Assigned Dependents".
    2. Enter "John@#123_$% " in the Name field.
    3. Select "Child" as the Relationship.
    4. Click the "Save" button.
*   **Expected Result:** The system should display a validation error (e.g., "Name can only contain letters") and block the record from saving.
*   **Actual Result:** The system successfully saved the record and displayed "John@#123_$%".
*   **Status:** Fail

---

### TC_OHRM_032
*   **Description:** Verify that the system prevents saving duplicate identical dependent records under the same employee profile.
*   **Pre-conditions:** User is logged in as Admin, is on the PIM Dependents page, and has already saved one dependent (Name: "John@#123_$% ", Relationship: "Child").
*   **Test Steps:**
    1. Click the "+ Add" button under "Assigned Dependents".
    2. Enter the identical details (Name: "John@#123_$% ", Relationship: "Child").
    3. Click the "Save" button.
*   **Expected Result:** The system should block the save and display an error message (e.g., "Duplicate dependent entry detected").
*   **Actual Result:** The system successfully saved the identical duplicate record, creating a redundant row.
*   **Status:** Fail
