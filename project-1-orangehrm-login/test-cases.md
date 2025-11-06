# OrangeHRM Login - Complete Test Cases

## Test Environment
- **Application URL:** https://opensource-demo.orangehrmlive.com/
- **Browser:** Chrome 142.0.7444.61
- **Operating System:** Windows 11
- **Test Date:** 11/6/2025
- **Test Type:** Manual Functional Testing

## Test Objectives
- Verify login functionality with valid and invalid credentials
- Validate password reset workflow
- Confirm error handling and user feedback
- Ensure security measures are properly implemented

## Key Findings & Learnings
- The application correctly implements security measures by showing generic error messages
- Form validation provides clear user feedback for required fields
- Password masking is properly implemented
- Forgot password flow follows security best practices to prevent username enumeration

## Test Execution Summary
- **Total Test Cases:** 12
- **Passed:** 12
- **Failed:** 0
- **Success Rate:** 100%
- **Date Executed:** 11/6/2025

## Detailed Test Cases

### Login Functionality

| ID | Scenario | Test Steps | Test Data | Expected Result | Status | Notes                |
|----|----------|-------------|-----------|----------------|--------|----------------------|
| TC-L-01 | Successful Login with Valid Credentials | 1. Navigate to OrangeHRM login page.<br>2. Enter valid username.<br>3. Enter valid password.<br>4. Click 'Login' button. | Username: Admin<br>Password: admin123 | User is successfully logged in. Dashboard page is displayed. | Pass | Happy Path           |
| TC-L-02 | Login with Invalid Username & Valid Password | 1. Navigate to OrangeHRM login page.<br>2. Enter invalid username.<br>3. Enter valid password.<br>4. Click 'Login' button. | Username: InvalidUsername<br>Password: admin123 | Login fails. Error message: "Invalid credentials" is displayed. | Pass | EP: Invalid Username |
| TC-L-03 | Login with Valid Username & Invalid Password | 1. Navigate to OrangeHRM login page.<br>2. Enter valid username.<br>3. Enter invalid password.<br>4. Click 'Login' button. | Username: Admin<br>Password: WrongPassword | Login fails. Error message: "Invalid credentials" is displayed. | Pass | EP: Invalid Password |
| TC-L-04 | Login with Empty Username | 1. Navigate to OrangeHRM login page.<br>2. Leave username empty.<br>3. Enter valid password.<br>4. Click 'Login' button. | Username: (empty)<br>Password: admin123 | Login fails. Error message: "Required" is displayed under the Username field. | Pass | EP: Empty Field      |
| TC-L-05 | Login with Empty Password | 1. Navigate to OrangeHRM login page.<br>2. Enter valid username.<br>3. Leave password empty.<br>4. Click 'Login' button. | Username: Admin<br>Password: (empty) | Login fails. Error message: "Required" is displayed under the Password field. | Pass | EP: Empty Field      |
| TC-L-06 | Login with Both Fields Empty | 1. Navigate to OrangeHRM login page.<br>2. Leave both fields empty.<br>3. Click 'Login' button. | Username: (empty)<br>Password: (empty) | Login fails. Error message: "Required" is displayed under both fields. | Pass | EP: Empty Field      |
| TC-L-07 | Verify Password is Masked | 1. Navigate to OrangeHRM login page.<br>2. Enter any text in the password field. | Password: admin123 | Characters are obscured (shown as bullets or asterisks) | Pass | Security Behavior    |

### Forgot Password Functionality

| ID | Scenario | Test Steps | Test Data                 | Expected Result | Status | Notes |
|----|----------|-------------|---------------------------|----------------|--------|-------|
| TC-FP-01 | Navigate to Forgot Password Page | 1. Navigate to login page.<br>2. Click 'Forgot your password?' link. | N/A                       | User is redirected to the password reset request page. | Pass | |
| TC-FP-02 | Successful Password Reset Request | 1. Navigate to Forgot Password page.<br>2. Enter a valid username.<br>3. Click 'Reset Password'. | Username: Admin           | A success message is displayed indicating reset instructions have been sent. | Pass | |
| TC-FP-03 | Reset Request with Invalid Username | 1. Navigate to Forgot Password page.<br>2. Enter an invalid username.<br>3. Click 'Reset Password'. | Username: invalidUsername | A success message is displayed (security measure to prevent username enumeration). | Pass | Security Behavior |
| TC-FP-04 | Reset Password with Empty Username | 1. Navigate to Forgot Password page.<br>2. Leave username field empty.<br>3. Click 'Reset Password'. | Username: (empty)         | Error message: "Required" is displayed. | Pass | EP: Empty Field |
| TC-FP-05 | Cancel Password Reset | 1. Navigate to Forgot Password page.<br>2. Click 'Cancel' button. | N/A                       | User is redirected back to the login page. | Pass | |

## Test Design Methodology
- **Equivalence Partitioning (EP)**: Used to group test inputs into valid/invalid/empty categories
- **Positive & Negative Testing**: Covered both successful and error scenarios
- **Security Considerations**: Verified password masking and username enumeration prevention
