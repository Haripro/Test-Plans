## Regression Test Strategy for Amazon Shopping - Version upgrade (v1 --> v2)

### Table of contents
1. Introduction
2. Test scope
3. Automation Test Strategy
4. Manual Test Strategy
5. Test Reporting
6. Timeline
7. Sign-off

### Introduction
In Amazon shopping experience, a new functionality i.e. New mode of payment, is introduced. This document captures the test strategy of customer-facing components for running regression tests with this feature change. The details of functionality change can be found [here](https://).

### Test Scope

The following components/modules are identified to be customer-facing components and the same shall be focussed during testing.
1. Functional Tests:
    * Catalog listing & categorization
    * Shopping Cart functionalities
    * Session Management
    * Profile Management
    * Order Management
    * Payment & Checkout
2. Non-functional Tests:
    * Usability Testing (All screens in the functional testing flow)
    * Compatability Testing
    * Performance Testing (Load testing)
    * Security Testing

### Automation Test Strategy



| Automation Type  | Strategy |
| -------- | -------- |
| Functional Tests     | Identify the automated tests that needs maintanence and perform the maintanence post testing. Run the unimpacted cases on priority|
| Non-functional (Compatability Tests)| Run the identified tests from functional regression suite, across multiple browswers and devices| 
| Non-functional (Load Tests) | Run the regression suite of load tests since they don't need any maintanence efforts| @John Doe|
| Security Testing| Input validation and Sanitization testing

*Example automated tests assuming they are already automated and not impacted with the change*



| #   | Test type                             | Test Category      | Test case                      | Test Tools |
| --- | ------------------------------------- | ------------------ | ------------------------------ | ---------- |
| 1   | Functional, Compatability, Usability, Security | Session Management | Verify the login & logout functionality | Selenium, appium   |
| 2    |     Functional, Compatability, Usability |Catalog & Categorization|Verify the products are listed with details|Selenium, appium |
|3|Functional, Compatability, Usability | Catalog & Categorization| Verify the CRUD of product categorization| Selenium, appium|
|4| Functional| Profile Management | Verify the CRUD of profile details | Selenium |
|5| Order Management | Order Management|Verify the CRUD of orders | Selenium |
|6| Load test | Payment, product launch| Verify that the respective systems able to handle the load of Payments, Product details, etc.,| Load testing tool |
|7| Security test | User Input| Verify the sanitization of malicious user input| xyzInspector|



### Manual Test Strategy
|Test Type| Strategy |
|----|----|
|Functional Tests| Run the tests in latest stable version of standard Chrome browser|
|Combatability Tests| Run the tests in chrome/firefox/safari/IE across Windows/Linux/MacOs systems. For mobile app automation use appium to run in android/IOS plaform/simulation. For mobile browswer automation, use appium to run in chrome/firefox/Android Browswer/IOS browser across Android & IOS system|
|Usability Tests| Validate the user facing flows are in compliant with accessibility standards such as WCAG and Section 508, etc.,

|#| Test type| Test Category | Test Case |
|---|-----|-----|-----|
|1| Functional, compatability| Order Management, Chekcout & Payments |Verify the successful order placement using different payment methods|
|2| Functional, compatability| Product & Categorization|Verify the successful product listing |
|3| Functional, compatability | Checkout & Payments| Verify correct failure message is shown for invalid/Failed payemnts|
|4| Functional, compatability |Product & Categorization |Verify correct failure message is show for duplicate listing| 
|5| Functional, compatability | Order Management|Verify the shipping options and estimations are displayed correctly| |
|6| Security | Usability/Visual assistance |Verify if the application is screen-reader friendly for visual assistance|

### Test Management

* **Automated Test Scripts** - Git Test branch for device tests & Pre-prod pipeline stage for automated tests
* **Test Case Management** - Test Rail [Suite](suite) 

* **Bug reporting** - In JIRA with the following lable v2-regression
* **Test Results** - Continuously updated in Confluence over the course of testing

### Timeline

*The timeline is drafted based on the priority and importance of features under test*

|Test type| Duration | Priority |
|-----|-----|-----|
|Automation testing (functional)| 2 days | P0|
|Automation testing (load/Security) | 1 day| P0 |
|Manual testing (functional)| 5 days|P0|
|Manual testing (non-functional except usability)| 3 days| P1|


### Sign-off

|Role|Reveiwer|Last Updated|Notes|
|---|---|---|---|
| TechLead/SDE| @Jane |
|STO/QAM| @John|
|QAE|@Jane Doe
