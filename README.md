# Telnyx-Webdriverio-POM-Allure

## Summary

This repository contains an automated testing framework for [Telnyx.com](https://telnyx.com) using WebdriverIO with Page Object Model (POM) design pattern, Allure reporting, and JavaScript. The test suite is containerized using Docker, making it easy to set up and run in any environment.

The project demonstrates best practices for web application testing, including:
- Page Object Model implementation for better test maintenance
- Cross-browser testing capabilities (Chrome, Firefox, Edge)
- Comprehensive test reporting using Allure
- Containerized test execution using Docker

## Requirements

- Node.js 
- npm 
- Docker (for containerized execution)
- Java Runtime Environment (JRE) - required for Allure reporting

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/Telnyx-Webdriverio-POM-Allure.git
   cd Telnyx-Webdriverio-POM-Allure
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Install Allure command-line tool globally:
   ```bash
   npm install -g allure-commandline
   ```

## Running Tests

### Local Execution

Run all tests using the default configuration:
```bash
npm run test
```

### Browser-Specific Tests

Run tests in specific browsers:

- Chrome:
  ```bash
  npm run test:chrome
  ```

- Firefox:
  ```bash
  npm run test:firefox
  ```

- Edge:
  ```bash
  npm run test:edge
  ```

### Run Specific Test Suites

- Run only pricing tests in Chrome:
  ```bash
  npm run test:chrome:pricing
  ```

- Run only home page tests in Edge:
  ```bash
  npm run test:edge:home
  ```

## Docker Execution

1. Build the Docker image:
   ```bash
   docker build -t telnyx-webdriverio-tests .
   ```

2. Run tests in Docker container:
   ```bash
   docker run -it telnyx-webdriverio-tests npm test
   ```

   For specific browser testing:
   ```bash
   docker run -it telnyx-webdriverio-tests npm run test:chrome
   ```

## Generating and Viewing Allure Reports

1. Generate the Allure report from test results:
   ```bash
   npm run allure:generate
   ```

2. Open the Allure report in your default browser:
   ```bash
   npm run allure:open
   ```

### Docker Report Generation

If you're running tests in Docker and want to access the Allure reports:

1. Run the tests with a volume mount:
   ```bash
   docker run -it -v $(pwd)/allure-results:/app/allure-results telnyx-webdriverio-tests npm test
   ```

2. Generate and view the report locally:
   ```bash
   npm run allure:generate
   npm run allure:open
   ```

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request
