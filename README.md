# 🧪 NHS Jobs Search Automation Suite – `KiruthikaArjunan-NHSBSA`

## 🔍 Project Overview

This project automates the **Search functionality** of the [NHS Jobs website](https://www.jobs.nhs.uk/candidate/search) using a **User-Centric BDD approach** with **Java 21**, **Selenium WebDriver**, **Cucumber**, and **JUnit**. It is built to validate job search behaviors across various user scenarios, supporting both functional and cross-browser validation.

---

## 📘 User Story

> **As a jobseeker on the NHS Jobs website**  
> I want to search for a job with my preferences  
> So that I can get recently posted job results

---

## ✅ Acceptance Criteria

- **Given** I am a jobseeker on NHS Jobs website  
- **When** I enter my preferences into the search functionality  
- **Then** I should get a list of jobs that match my preferences  
- **And** I can sort my results by Date Posted (newest)

---

## 💻 Tech Stack

| Technology         | Purpose                                        |
|--------------------|------------------------------------------------|
| Java 21            | Programming language                           |
| Maven              | Build and dependency management                |
| Selenium WebDriver | Web automation library                         |
| Cucumber (Gherkin) | BDD test framework                             |
| JUnit              | Test runner integration                        |
| WebDriverManager   | Driver management for Chrome & Firefox         |
| Log4j              | Logging of test execution                      |

---

## 📂 Project Structure

```
NHSBSA/
├── src/
│   ├── main/
│   │   └── java/
│   │       └── utils/
│   │           ├── DriverFactory.java       # WebDriver setup (Chrome/Firefox)
│   │           └── LoggerHelper.java        # Log4j configuration
│
│   └── test/
│       ├── java/
│       │   ├── runners/
│       │   │   └── NHSTestRunner.java          # Cucumber test runner
│       │   ├── steps/
│       │   │   └── NhsJobSearchSteps.java   # Step definitions for NHS search
│       └── resources/
│           ├── features/
│           │   └── NHSJobSearch.feature       # BDD feature file
│           └── logs/
│               └── log4j.properties         # Log4j configuration
│
├── logs/
│   └── automation.log                       # Execution logs
├── pom.xml                                  # Maven build config
└── README.md                                # Project documentation
```

---

## 🎯 Test Coverage

This suite thoroughly validates the **Search functionality** with a wide range of test scenarios:

### 🔹 Functional Scenarios

- ✅ Job search with title, location, distance, reference, employer, and pay range
- ✅ Validation of dropdown selections and input field retention
- ✅ Search results sorting by "Date Posted (newest)"
- ✅ Clear filters and reset behavior
- ✅ Field hint and placeholder validations
- ✅ Search with all fields empty

### 🔹 UI Validations

- ✅ Default selections in dropdowns (Distance, Pay Range, Sort By)
- ✅ Dynamic enabling/disabling of Distance dropdown based on Location
- ✅ Suggestions for valid/invalid location input
- ✅ Error message display for invalid inputs

### 🔹 Negative and Edge Cases

- ✅ Misspelled or numeric locations
- ✅ Invalid job references and fake employers
- ✅ Special characters and mixed input in search fields
- ✅ No suggestions shown for unsupported input

### 🔹 Cross-Browser Support

- ✅ Tests run in **Chrome**
- ✅ Tests run in **Firefox**
- ✅ No machine-bound drivers (WebDriverManager handles setup dynamically)

---

## ⚙️ How to Run the Tests

### 🔧 Prerequisites

- Java 21+
- Maven 3.8+
- Internet connection

### 📥 Clone the Repository

```bash
git clone https://github.com/akiruthikaArjunan/kiruthika-NHSBSA.git
cd kiruthika-NHSBSA
```

### ▶️ Run All Tests

#### Run in Chrome:

```bash
mvn clean test -Dbrowser=chrome
```

#### Run in Firefox:

```bash
mvn clean test -Dbrowser=firefox
```


### 🎯 Run Tests by Tags

| Tag Combination            | Command                                                                 |
|----------------------------|-------------------------------------------------------------------------|
| Only happy path tests      | mvn clean test "-Dcucumber.filter.tags=@happy" "-Dbrowser=chrome"     |
| Only UI validation tests   | mvn clean test "-Dcucumber.filter.tags=@ui" "-Dbrowser=chrome"        |
| Only negative tests        | mvn clean test "-Dcucumber.filter.tags=@unhappy" "-Dbrowser=chrome"   |
| Happy + UI tests           | mvn clean test "-Dcucumber.filter.tags=@happy or @ui" "-Dbrowser=chrome" |
| All tests                  | mvn clean test "-Dcucumber.filter.tags=@happy or @ui or @unhappy" "-Dbrowser=chrome" |

You can switch `-Dbrowser=chrome` to `firefox` as needed.

---

## 🧾 Test Reports & Logs

- **HTML Report**:  
  `target/cucumber-reports/report.html`

- **Log File**:  
  `logs/automation.log`

---

## 🌱 Enhancements (Future Work)

- ✅ Add parallel execution with Cucumber-JUnit or Cucumber-TestNG
- ✅ Add support for headless browser execution for CI pipelines
- ✅ Integrate with BrowserStack or Sauce Labs for broader browser/device coverage
- ✅ Introduce accessibility checks using Axe or Lighthouse
- ✅ Extend with API-level validations (if APIs are exposed)
- ✅ Dockerize test execution for container-based pipelines
- ✅ Generate dynamic test data by reading from CSV or Excel files for flexible and maintainable test inputs
- ✅ Add retry mechanism for flaky steps
- ✅ Integrate with Allure for rich test reporting
- ✅ Enable test result email notifications after execution
- ✅ Use AWS S3 bucket to securely store and manage test execution reports for easy access and archival

---

## 👤 Author

**Kiruthika Arjunan**  
📧 [a.kiruthika@gmail.com]  
🔗 [https://github.com/akiruthikaArjunan/kiruthika-NHSBSA](https://github.com/akiruthikaArjunan/kiruthika-NHSBSA)

## Documentation

[Documentation](https://linktodocumentation)

