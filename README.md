# DemoBlazeWebsiteProject
DemoBlaze is an online e-commerce platform that offers a variety of digital devices, including mobile phones, laptops, and monitors.

Title Of the Project : Mini project Demoblaze website

URL                  :www.demoblaze.com/

Abstract   :
			    This project is an automation testing framework developed using Java, Selenium WebDriver, TestNG,Data Driven and the Page Object Model (POM) design pattern to test the end-to-end functionalities of the Demoblaze web application.
Demoblaze is an online shopping portal offering various electronic products. This test automation project aims to validate critical workflows such as user login, product selection, cart management, payment, and logout functionalities. The primary goal is to ensure the application behaves as expected across multiple scenarios by automating repetitive manual testing tasks.
This framework promotes modularity, reusability, and maintainability by separating the page logic from the test logic using POM. Test execution and reporting are handled through TestNG, and browser interactions are driven by Selenium WebDriver.

🔧 Technologies Used  :

Programming Language: Java

Automation Tool: Selenium WebDriver

Test Framework: TestNG

Design Pattern: Page Object Model (POM)

Build Tool: Maven

Reporting: Extent Reports

Browser: Chrome (via ChromeDriver),FireFox,Edge etc.


✅ Key Features  :

Modular test scripts following best practices

Custom utility classes for reusable wait methods and browser handling

Clear separation of concerns using POM

Data-driven testing capability (Excel/Properties files)

Detailed logging and Extent reporting with screenshots on failure


🔧 Installation Steps  :
To run the test automation suite for the Demoblaze application, follow the steps below:

Prerequisites:
Java 21 or above installed on your system.

Maven for dependency management.

Eclipse IDE or any other Java IDE (like IntelliJ IDEA).

Chrome Browser (other browsers can be configured based on requirements).

ChromeDriver: Ensure you have the appropriate version of ChromeDriver that matches your browser version.


Project Flow for Maven Selenium TestNG Framework with Page Object Model (POM) and Utilities :

The framework will include several components such as base classes, utilities, page classes, and test cases, as well as mechanisms for logging, reporting, and data handling.
Project Components
Selenium WebDriver:

Selenium is used for automating the interaction with the browser. It drives the browser and performs actions like clicking buttons, entering text, and verifying page elements to ensure that the web application is functioning as expected.

TestNG:

TestNG is a testing framework for Java that helps in organizing and running test cases. It provides several advanced features such as grouping tests, prioritizing tests, and generating reports. It also supports parallel execution, making it easier to execute tests on multiple browsers or configurations simultaneously.

Page Object Model (POM):

The Page Object Model is a design pattern that creates an object-oriented class to serve as an interface to a web page. POM improves test maintainability by separating the logic of interactions with web elements from the actual test scripts, making it easier to update and scale tests when the application UI changes.

Reporting and Utility:

ExtentReports is used for generating detailed HTML reports with visual and textual insights about the test execution. This allows developers and testers to get a clear understanding of which tests passed, failed, and any issues that occurred.

Utilities like Excel Reader, Waits, Alerts, and Screenshot Capture are created to handle specific tasks, such as reading data from an Excel sheet for data-driven testing, adding synchronization (waits), handling pop-ups, and capturing screenshots when test failures occur.



1)Project Structure  :

Below is the proposed directory structure for the project:

demo-maven-project/
├── pom.xml                     --> Maven Configuration
├── src
│   ├── main
│   │   ├── java
│   │   │   ├── com
│   │   │   │   ├── qa
│   │   │   │   │   ├── base              --> Base class for WebDriver initialization
│   │   │   │   │   ├── pages             --> Page Object Model classes
│   │   │   │   │   ├── test              --> Test cases
│   │   │   │   │   ├── utilities         --> Utility classes for reading Excel, screenshots, waits, alerts
│   ├── test
│   │   ├── java
│   │   │   ├── com
│   │   │   │   ├── qa
│   │   │   │   │   ├── test              --> Test classes for functional tests
│   │   ├── resources
│   │   │   ├── data                   --> Excel data files
│   │   │   ├── report-snap            --> Folder for storing screenshots and logs
│   │   │   ├── testng.xml             --> TestNG XML configuration for running tests
│   │   │   ├── extent-config.xml      --> ExtentReports configuration


2) Key Components
a. pom.xml (Maven Configuration)
This file defines the project's dependencies and plugins used to run the test suite, generate reports, and manage the Selenium WebDriver and TestNG versions.

<project xmlns="http://maven.apache.org/POM/4.0.0"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<groupId>org.guvi</groupId>
	<artifactId>GuviMiniProject</artifactId>
	<version>0.0.1-SNAPSHOT</version>


	<dependencies>

		<!--https://mvnrepository.com/artifact/org.seleniumhq.selenium/selenium-java -->
		<dependency>
			<groupId>org.seleniumhq.selenium</groupId>
			<artifactId>selenium-java</artifactId>
			<version>4.30.0</version>
		</dependency>
		<!-- https://mvnrepository.com/artifact/org.testng/testng -->
		<dependency>
			<groupId>org.testng</groupId>
			<artifactId>testng</artifactId>
			<version>7.8.0</version>
			<scope>test</scope>
		</dependency>

		<!-- https://mvnrepository.com/artifact/org.apache.poi/poi -->
		<dependency>
			<groupId>org.apache.poi</groupId>
			<artifactId>poi</artifactId>
			<version>5.4.0</version>
		</dependency>

		<!-- https://mvnrepository.com/artifact/org.apache.poi/poi-ooxml -->
		<dependency>
			<groupId>org.apache.poi</groupId>
			<artifactId>poi-ooxml</artifactId>
			<version>5.4.0</version>
		</dependency>


		<dependency>
			<groupId>com.aventstack</groupId>
			<artifactId>extentreports</artifactId>
			<version>5.1.2</version>
		</dependency>
		<!-- https://mvnrepository.com/artifact/com.aventstack/extentreports -->


		<!-- Log4j2 API -->
		<dependency>
			<groupId>org.apache.logging.log4j</groupId>
			<artifactId>log4j-api</artifactId>
			<version>2.20.0</version> <!-- Latest stable version -->
		</dependency>

		<!-- Log4j2 Core -->
		<dependency>
			<groupId>org.apache.logging.log4j</groupId>
			<artifactId>log4j-core</artifactId>
			<version>2.20.0</version> <!-- Latest stable version -->
		</dependency>

		<!-- Log4j2 SLF4J Binding (optional if using SLF4J) -->
		<dependency>
			<groupId>org.apache.logging.log4j</groupId>
			<artifactId>log4j-slf4j-impl</artifactId>
			<version>2.20.0</version> <!-- Latest stable version -->
		</dependency>

		<!-- SLF4J binding for Logback -->
		<dependency>
			<groupId>ch.qos.logback</groupId>
			<artifactId>logback-classic</artifactId>
			<version>1.4.11</version>
		</dependency>

		<dependency>
			<groupId>org.guvi</groupId>
			<artifactId>Demoblazeproj</artifactId>
			<version>0.0.1-SNAPSHOT</version>
		</dependency>
	</dependencies>


	<name>MiniprojectDemoblaze</name>
	<description>A mini project using Selenium -javaI for automation and Excel
		operations</description> <!-- Optional: A short description of your
	project -->

</project>

Automation Flow
TestNG XML Configuration:

The test cases are organized and executed based on a testng.xml file. This file defines the suite, individual tests, and the classes to be executed. It allows us to specify which test cases should run, prioritize them, and manage configurations (like browser or environment settings).

Page Object Model (POM):

POM is implemented to separate the test logic from the UI interaction logic. Each page of the application has its own corresponding page object class, which contains methods for interacting with elements on that page.

For instance, the LoginPage class contains methods like enterUsername(), enterPassword(), and clickSubmitButton(), while the PaymentPage class contains methods to interact with payment form fields.

Test Classes:

The Test Classes (e.g., LoginTest, PurchaseTest) contain the actual test cases. Each test case is a method annotated with @Test that verifies a specific functionality of the web application.

These test methods typically:

Launch the browser and open the application.

Perform actions (like filling out a form, clicking a button).

Assert the expected results (e.g., verify the presence of a confirmation message).

Capture screenshots in case of failures and log the test results.

TestNG Listeners:

The project utilizes TestNG Listeners for enhanced control over test execution. ITestListener is used to handle test events, such as starting, passing, or failing. These listeners can log additional details, capture screenshots, and generate reports dynamically.

Utility Classes:

Utility classes like WaitHelper, ExcelReader, AlertHandler, and ScreenshotUtil make the test execution process smoother and more efficient:

WaitHelper: Helps in adding implicit and explicit waits to ensure elements are present and clickable before performing actions.

ExcelReader: Reads input data from Excel files for data-driven testing.

AlertHandler: Manages browser popups and alerts that might interrupt the test execution.

ScreenshotUtil: Captures screenshots on test failure, making debugging easier.


3)Project Components in Quick view

a. Base Class (ProjectSpecificationMethods)
The base class is used for WebDriver initialization, managing browser setups, and basic test setup.


b. Page Object Model (POM) Classes
Page Object Model classes represent different pages in your application and encapsulate actions that can be performed on those pages. For example, LoginPage.java, HomePage.java.


c. Test Classes
Test classes are responsible for performing the actual test actions by interacting with Page Objects. They are typically located in the test package.


4) Utility Classes

The utility package contains helper classes for tasks like waiting for elements, handling alerts, taking screenshots, and reading data from Excel files.


5) Listener Class for Reporting
   
TestNG Listeners are used to perform actions like logging, reporting, or taking screenshots when certain events occur during test execution. The listener class can be implemented to hook into the ITestListener interface.

6) Extent Report for Test Execution Reports
To integrate ExtentReports for generating visually rich reports, create a utility method to initialize the report, log test results, and generate the report after test execution.

7)  Create a testng.xml File

Create a testng.xml file in your src/test/resources folder (or anywhere under src).
Right click on project or test class Convert To Testng.
The testng.xml file will list the classes and methods that TestNG should run.

8)Run the Test from Eclipse
If we using Eclipse, you can follow these steps to run your tests from within the IDE:

Right-click on the testng.xml file in the src/test/resources folder.

Select Run As > TestNG Suite.

This will execute all the tests defined in the testng.xml file.

8)To View Reports

After running the tests, you can check the output in your target directory for TestNG reports or ExtentReports (if you've configured ExtentReports in your utilities).

TestNG Report: After running the tests, TestNG will generate an HTML report in the test-output directory (e.g., test-output/index.html).

Extent Report: If you've configured ExtentReports, the report will be generated at the path defined in your report utility (e.g., ./Reports/extentReport.html).

To view report -It will create the file --> folder created under test resources  
Example :C:\Users\ADMIN\eclipse-workspace1\GuviMiniProject\src\test\resources\Report\DemoblazeExtendreport.html
         DemoblazeExtendreport.html ---->Right click  ---->open --->web browser

  Note:This is the screenshot of the report :       ![image](https://github.com/user-attachments/assets/3330d3b8-03f4-40cf-890c-48b5437c9b8d)

Also Project --->test-output ----> emailable report -->Here also we can see the test report 

Key Benefits of This Automation Approach
Separation of Concerns (POM):

The Page Object Model makes tests easier to maintain. The separation of the page's UI interactions and the tests ensures that UI changes (like changing element locators) only require changes in the page object class, not in each individual test.

Scalability:

The framework is scalable and can handle multiple test cases across different pages. Adding new test cases, page classes, and test scenarios is simple.

With TestNG’s support for parallel execution, tests can be executed on different browsers simultaneously, reducing execution time.

Maintainability:

The utility classes and base classes (like ProjectSpecificationMethods) provide reusable code for repetitive tasks, such as initializing the WebDriver, handling waits, and reporting.

This minimizes code duplication and makes the codebase cleaner and more maintainable.

Cross-browser Compatibility:

The WebDriver setup supports multiple browsers, and the framework can be easily extended to support cross-browser testing (e.g., Chrome, Firefox, Edge).

Data-driven Testing:

With ExcelReader, data can be fed into the tests dynamically, allowing the same test case to run with different sets of data, ensuring better test coverage.

Error Handling and Reporting:

Screenshots on failure and detailed reports provide valuable insights into test execution, making it easier to debug issues.

Efficient Test Execution:

Using TestNG's parallel="true" attribute and properly configuring tests to run in parallel can drastically reduce the overall execution time for a large test suite.


Conclusion  :

This Automation Framework using Selenium WebDriver, TestNG, and the Page Object Model offers a robust and efficient solution for automating the functional testing of web applications. It enables faster and more reliable test execution, thorough reporting, and easy maintenance. By separating test logic from UI interaction logic, this approach ensures that the framework is scalable, flexible, and easier to manage.

The project's design, utilizing the POM framework, TestNG, and essential utilities, ensures that future modifications to the application’s UI or test scenarios can be managed with minimal effort. The reports generated through ExtentReports and TestNG allow the team to monitor test execution and quickly identify and address issues.

This project Demoblaze.com website offers a strong foundation for building a comprehensive automation suite, capable of handling large-scale and cross-browser tests efficiently, thus improving the quality and reliability of the web application under test.


Acknowledgment and Gratitude :

  I am truly grateful for the resources, expertise, and opportunities that GUVI has provided me throughout this Project.
