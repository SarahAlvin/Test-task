# test-task
Documentation Submitted by Sara Alvin
Test Plan Outline for Testing the Registration Form
1. Introduction
•	Purpose: To ensure the registration form functions correctly and meets the specified requirements.
•	Scope: Testing the validation, error handling, and submission functionalities of the registration form.
2. Objectives
•	Verify all input fields accept valid data.
•	Ensure proper error messages are displayed for invalid inputs.
•	Confirm successful submission of the form with correct data.
3. Scope
•	Functional Testing: Validation, error messages, and form submission.
•	Usability Testing: Ease of use and user experience.
•	Security Testing: Basic security checks (e.g., password requirements).
4. Test Environment
•	Browsers: Chrome, Firefox, Safari
•	OS: Windows, macOS, Linux
•	Devices: Desktop, Mobile
5. Test Data
•	Full Name: Sara Alvin, Alvin Joseph
•	Email Address: sara@gmail.com, alvin@gmail.com
•	Password: P@ssw0rd123
•	Date of Birth: 01/01/1999
•	Gender: Female, Male
•	Newsletter Subscription: Yes, No
6. Test Scenarios
•	Positive Scenarios:
1.	Valid data submission
2.	Optional fields left empty (e.g., Newsletter Subscription)
•	Negative Scenarios:
1.	Invalid email format
2.	Password and Confirm Password mismatch
7. Test Execution Schedule
•	Week 1: Test case creation and review
•	Week 2: Test execution and defect logging
•	Week 3: Defect retesting and final report
8. Risks and Assumptions
•	Risks: Browser compatibility issues, intermittent server issues.
•	Assumptions: Server is available, test environment is stable.
Test Cases
Test Case 1
•	Test Case ID: TC001
•	Test Case Description: Verify successful registration with valid data.
•	Preconditions: User is on the registration page.
•	Test Steps:
1.	Enter "Sara Alvin" in Full Name field.
2.	Enter "sara@gmail.com" in Email Address field.
3.	Enter "P@ssw0rd123" in Password field.
4.	Enter "P@ssw0rd123" in Confirm Password field.
5.	Enter "01/01/1999" in Date of Birth field.
6.	Select "Female" for Gender.
7.	Select "Yes" for Newsletter Subscription.
8.	Click the Submit button.
•	Expected Results: Registration is successful, and a confirmation message is displayed.
•	Post-conditions: User is registered, and data is submitted to the server.
Test Case 2
•	Test Case ID: TC002
•	Test Case Description: Verify error message for invalid email format.
•	Preconditions: User is on the registration page.
•	Test Steps:
1.	Enter "Sara Alvin" in Full Name field.
2.	Enter "sara@example" in Email Address field.
3.	Enter "P@ssw0rd123" in Password field.
4.	Enter "P@ssw0rd123" in Confirm Password field.
5.	Enter "01/01/1999" in Date of Birth field.
6.	Select "female" for Gender.
7.	Select "Yes" for Newsletter Subscription.
8.	Click the Submit button.
•	Expected Results: An error message "Invalid email format" is displayed.
•	Post-conditions: User is prompted to correct the email address.
Test Case 3
•	Test Case ID: TC003
•	Test Case Description: Verify error message for password mismatch.
•	Preconditions: User is on the registration page.
•	Test Steps:
1.	Enter "Alvin Joseph" in Full Name field.
2.	Enter "alvin@example.com" in Email Address field.
3.	Enter "P@ssw0rd123" in Password field.
4.	Enter "P@ssw0rd456" in Confirm Password field.
5.	Enter "01/01/1999" in Date of Birth field.
6.	Select "Male" for Gender.
7.	Select "Yes" for Newsletter Subscription.
8.	Click the Submit button.
•	Expected Results: An error message "Passwords do not match" is displayed.
•	Post-conditions: User is prompted to correct the passwords.
Scenario Identification
Positive Scenarios
1.	Scenario 1: Valid Data Submission
o	Steps: Fill in all fields with valid data and submit.
o	Expected Outcome: Registration is successful.
2.	Scenario 2: Optional Field Left Empty
o	Steps: Fill in all mandatory fields with valid data, leave Newsletter Subscription empty, and submit.
o	Expected Outcome: Registration is successful.
Negative Scenarios
1.	Scenario 1: Invalid Email Format
o	Steps: Enter an invalid email address and submit.
o	Expected Outcome: Error message "Invalid email format."
2.	Scenario 2: Password Mismatch
o	Steps: Enter different values for Password and Confirm Password, and submit.
o	Expected Outcome: Error message "Passwords do not match."




Test Writing
Automated Test Scripts

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.Assert;
import org.testng.annotations.AfterMethod;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.Test;

public class RegistrationFormTests {
    private WebDriver driver;

    @BeforeMethod
    public void setUp() {
        // Set the path for the ChromeDriver
        System.setProperty("webdriver.chrome.driver", "path/to/chromedriver"); 
        driver = new ChromeDriver();
        driver.get("https://mdbootstrap.com/#"); // 
    }

    @AfterMethod
    public void tearDown() {
        driver.quit();
    }

    @Test
    public void testSuccessfulRegistrationWithValidData() {
        WebElement fullName = driver.findElement(By.name("Your name"));
        WebElement email = driver.findElement(By.name("email"));
        WebElement password = driver.findElement(By.name(" Your password"));
        WebElement confirmPassword = driver.findElement(By.name("Repeat Password"));
        WebElement submitButton = driver.findElement(By.cssSelector("button[type='Sign up']"));

        fullName.sendKeys("John Doe");
        email.sendKeys("john@example.com");
        password.sendKeys("P@ssw0rd123");
        confirmPassword.sendKeys("P@ssw0rd123");
        submitButton.click();

        WebElement successMessage = driver.findElement(By.id("successMessage")); // Replace with actual element identifier
        Assert.assertTrue(successMessage.isDisplayed(), "Registration was not successful.");
    }

    @Test
    public void testSuccessfulRegistrationWithOptionalFieldsEmpty() {
        WebElement fullName = driver.findElement(By.name("Your name"));
        WebElement email = driver.findElement(By.name("email"));
        WebElement password = driver.findElement(By.name(" Your password"));
        WebElement confirmPassword = driver.findElement(By.name("Repeat Password");
        WebElement submitButton = driver.findElement(By.cssSelector("button[type='Sign up']"));

        fullName.sendKeys("John Doe");
        email.sendKeys("john@example.com");
        password.sendKeys("P@ssw0rd123");
        confirmPassword.sendKeys("P@ssw0rd123");
        submitButton.click();

        WebElement successMessage = driver.findElement(By.id("successMessage")); // Replace with actual element identifier
        Assert.assertTrue(successMessage.isDisplayed(), "Registration was not successful.");
    }
}
// I was unable to find any website containing all these fields that’s why I used this one. 
