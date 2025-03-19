# demoMFA
A Spring Boot application integrating Okta for OAuth 2.0 authentication and Multi-Factor Authentication (MFA).

## Overview
This project demonstrates how to secure a Spring Boot application using Okta's OAuth 2.0 and MFA capabilities. It includes a basic REST endpoint protected by authentication and authorization.

## Features
- **Okta OAuth 2.0 Integration**: Users are authenticated through Okta using OAuth 2.0.
- **Multi-Factor Authentication (MFA)**: MFA is enforced during the authentication flow for enhanced security.
- **JWT Token Generation**: After successful authentication, a JWT token is generated for subsequent requests.

## Prerequisites
- **Java 23 or Higher**: Required for running the application.
- **Okta Account**: A free Okta developer account is needed for setting up the OAuth 2.0 and MFA configurations.
- **Maven or Gradle**: Build tools for managing dependencies.

## Setup Instructions

### Step 1: Clone the Repository
Clone this repository to your local machine.

```bash
git clone https://github.com/hemanth-2711/DemoMFA.git
```

### Step 2: Configure Okta
1. **Create an Okta Application**:
   - Log in to your Okta dashboard and create a new web application.
   - Note the client ID and client secret.

2. **Configure MFA**:
   - Set up MFA policies in Okta to require MFA for your application.

### Step 3: Update Application Properties
1. **Update `application.properties`**:
   - Set the Okta issuer URL, client ID, and client secret.

   ```properties
   spring.application.name=demoMFA
   okta.oauth2.issuer=https://dev-18473988.okta.com/oauth2/default/
   okta.oauth2.client-id=0oanudphreWkXyAIm5d7
   okta.oauth2.client-secret=Rh1uqQRQpXThP5M-I5MbWluD3tP-_6pWATSfZizu-nLyjZ_fBKo1wAhFJ-w3SH3G
   server.port=8080
   ```

2. **Disable DevTools if Necessary**:
   - If you encounter issues with DevTools, you can disable it by adding:

   ```properties
   spring.devtools.add-properties=false
   ```

### Step 4: Run the Application
1. **Build and Run**:
   - Use Maven or Gradle to build and run the application.

   ```bash
   mvn spring-boot:run
   ```

   or

   ```bash
   ./gradlew bootRun
   ```

### Step 5: Test the Application
1. **Access Protected Endpoint**:
   - Navigate to `http://localhost:8080/hello` in your browser.
   - You should be redirected to Okta for authentication.
   - After successful authentication and MFA completion, you should see the "Hello, World!" message.

## Troubleshooting
- **Okta Issuer URL Mismatch**:
  Ensure that the Okta issuer URL in your application properties matches the one in your Okta configuration.
- **SecurityFilterChain Issue**:
  Verify that you have the correct version of Spring Security in your project.

## Contributing
Contributions are welcome! Please submit pull requests with detailed explanations of changes.




