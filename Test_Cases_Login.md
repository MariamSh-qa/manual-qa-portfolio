## Test Cases for Login functionality. 
---


**ID: TC_001**

**Title:**  Verify login with valid credentials

**Priority:**
   High 

**Preconditions:**  User must be on the login page and User should exist. 

**Steps:**
1. Enter valid username
2. Enter valid password
3. Click on Login button

**Expected Result:**

User should be successfully logged in and redirected to the dashboard





## ID: ""TC_002""

**Title:** 
Verify login with invalid password

**Priority:**
High

**Preconditions:**
User must be on the login page and user shouls exist. 

**Steps:**
1. Enter valid username
2. Enter incorrect password
3. Click on Login button

**Expected Result:**
Error message should be displayed: "Invalid username or password"


## ID: TC_003

**Title:**
Verify login with empty fields

**Priority:**
High 

**Preconditions:**
User must be on the login page

**Steps:**
1. Leave username field empty
2. Leave password field empty
3. Click on Login button

**Expected Result:**
Validation messages should appear for required fields




