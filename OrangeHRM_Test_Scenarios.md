# OrangeHRM ERP High-Level Test Scenarios

This document outlines the 20 high-level test scenarios identified during the requirement analysis phase of the OrangeHRM Enterprise Resource Planning (ERP) application.

---

### User Authentication & Session Security
*   **TS_001:** Verify system behavior and error display when attempting to log in with an invalid username.
*   **TS_002:** Verify successful login when using valid credentials.
*   **TS_003:** Verify redirection to the reset password page when clicking the 'Forgot your password?' link.
*   **TS_004:** Verify that attempting to access the dashboard URL directly without an active session redirects back to the login page (Session Security).

### PIM (Personnel Information Management) Module
*   **TS_005:** Verify that the system displays matching records when searching by a valid Employee Name.
*   **TS_006:** Verify that the system displays matching records when searching by a valid Employee ID.
*   **TS_007:** Verify that the 'Reset' button clears all active search filters and restores the default employee list.
*   **TS_008:** Verify error handling when attempting to save a new employee with the mandatory 'First Name' field left blank.
*   **TS_009:** Verify error handling when attempting to save a new employee with the mandatory 'Last Name' field left blank.
*   **TS_010:** Verify error handling when attempting to upload a file that is not in a supported format (.jpg, .png, or .gif) as a profile picture.
*   **TS_011:** Verify error handling when attempting to upload a profile picture that is larger than the 1MB file size limit.
*   **TS_012:** Verify that enabling the 'Create Login Details' toggle expands the form to display the username, status, and password fields.
*   **TS_013:** Verify that a standard .jpg image under 1MB uploads successfully as a profile picture.
*   **TS_014:** Verify that edits made to an employee's profile (e.g., Blood Type or License Number) on the 'Personal Details' page are successfully saved.
*   **TS_015:** Verify that a user can successfully upload an attachment (like a contract or resume) to an employee's profile.
*   **TS_016:** Verify that changes made to an employee's contact details (such as email or telephone) are successfully saved.
*   **TS_017:** Verify that a user can add emergency contact details for an employee.
*   **TS_018:** Verify system behavior and deletion confirmation popup when selecting multiple employees from the list and clicking the 'Delete Selected' button.
*   **TS_019:** Verify that the Employee List can be sorted by Employee ID in ascending and descending order.

### Reports & Configuration
*   **TS_020:** Verify that the search results table updates dynamically when searching for a report using a partial matching keyword.
*   **TS_021:** Verify that the 'Type for hints...' search bar auto-suggests existing reports as the user types keywords.
*   **TS_022:** Verify that clicking the 'Add' button under reports displays the new input fields required for creating a report.

### System Administration & User Management
*   **TS_023:** Verify error handling and validation message when attempting to add a new system user with a username that already exists.
*   **TS_024:** Verify that the system user search list filters correctly when searching by User Role (Admin/ESS).
*   **TS_025:** Verify that a newly created job title is successfully saved and appears in the Job Titles list.
*   **TS_026:** Verify that a system user can be successfully deleted from the Admin User list.
*   **TS_027:** Verify that the system user search list filters correctly when searching by status (Enabled/Disabled).
*   **TS_028:** Verify that the top navigation bar profile dropdown expands and collapses correctly.
*   **TS_029:** Verify that logging out successfully terminates the active user session and redirects to the login page.
