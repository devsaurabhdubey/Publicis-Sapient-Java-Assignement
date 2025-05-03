# User Search Application

## Contact

* Email: [saurabhdubey097@gmail.com](mailto:saurabhdubey097@gmail.com)
* WhatsApp: +7080778440

## Table of Contents

* [Backend API](#backend-api)
    * [Description](#description-backend)
    * [Details](#details-backend)
    * [Dataset](#dataset-backend)
    * [Technology Stack](#technology-stack-backend)
    * [Prerequisites](#prerequisites-backend)
    * [Getting Started](#getting-started-backend)
        * [1\. Project Setup](#1-project-setup-backend)
        * [2\. Configuration](#2-configuration-backend)
        * [3\. Running the Application](#3-running-the-application-backend)
        * [4\. API Documentation](#4-api-documentation-backend)
    * [API Endpoints](#api-endpoints-backend)
        * [Loading Data](#loading-data-backend)
        * [Retrieving Data](#retrieving-data-backend)
* [Frontend UI](#frontend-ui)
    * [Description](#description-frontend)
    * [Details](#details-frontend)
    * [Technology Stack](#technology-stack-frontend)
    * [Prerequisites](#prerequisites-frontend)
    * [Getting Started](#getting-started-frontend)
        * [1\. Project Setup](#1-project-setup-frontend)
        * [2\. Configuration](#2-configuration-frontend)
        * [3\. Running the Application](#3-running-the-application-frontend)
    * [Key Features](#key-features-frontend)

#   Backend API

##  Description

This backend API is designed to load user data from an external dataset into a local in-memory database (H2) and provide RESTful endpoints to retrieve users based on various criteria.

##  Details

* **Question:** Orchestration API to load data from the external dataset into local in-memory DB, and then provide REST endpoints to fetch the users based upon various user criteria.

##  Dataset

The API utilizes the following external dataset:

* URL: [DummyJSON Users](https://dummyjson.com/users)

##  Technology Stack

* Programming Language: \[Specify, e.g., Java, Kotlin, etc.]
* Framework: \[Specify, e.g., Spring Boot, Node.js, etc.]
* Database: H2 (in-memory)
* Documentation: Swagger/OpenAPI
* Testing: \[Specify, e.g., JUnit, Jest, etc.]
* Build Tool: \[Specify, e.g., Maven, Gradle, npm, etc.]

##  Prerequisites

* Java Development Kit (JDK) \[Version]
* \[Specify other dependencies, e.g., Maven, Gradle, Node.js, etc.]
* A suitable IDE (e.g., IntelliJ IDEA, Eclipse, VS Code)
* (Optional) A REST client for testing (e.g., Postman, Insomnia)

##  Getting Started

### 1\. Project Setup

* \[Provide instructions on how to clone the repository, if applicable, or how to create a new project and add the necessary dependencies.]
* Example (for Spring Boot):

    1.  Clone the repository:

        \`\`\`bash
        git clone <repository\_url>
        \`\`\`

    2.  Navigate to the project directory:

        \`\`\`bash
        cd <project\_directory>
        \`\`\`

    3.  Build the project:

        \`\`\`bash
        ./mvnw clean install
        \`\`\`

        (Maven)

        \`\`\`bash
        ./gradlew build
        \`\`\`

        (Gradle)

### 2\. Configuration

* The application uses externalized configuration.
* \[Explain how to configure environment-specific settings, e.g., using `application.properties` or environment variables in Spring Boot.  Specify any configuration parameters, such as:]
    * Port number
    * External API URL
    * H2 database settings (if applicable)
    * Any API keys
* Example (for Spring Boot):

    Create an `application.properties` file in the `src/main/resources` directory.

    Example properties:

    \`\`\`properties
    server.port=8080
    external.api.url=https://dummyjson.com/users
    spring.datasource.url=jdbc:h2:mem:userdb;DB_CLOSE_DELAY=-1
    spring.datasource.driverClassName=org.h2.Driver
    spring.datasource.username=sa
    spring.datasource.password=
    spring.jpa.defer-datasource-initialization=true #Important
    \`\`\`

### 3\. Running the Application

* \[Provide detailed instructions on how to run the application.]
* Example (for Spring Boot):
    * Using Maven:

        \`\`\`bash
        ./mvnw spring-boot:run
        \`\`\`

    * Using Gradle:

        \`\`\`bash
        ./gradlew bootRun
        \`\`\`

    * From your IDE: Run the main class.

### 4\. API Documentation

* The API is documented using Swagger/OpenAPI.
* Once the application is running, you can access the API documentation at the following URL:
    * `http://localhost:[port]/swagger-ui/index.html`
    * (Adjust the port if you have configured it differently.)

##  API Endpoints

### Loading Data

* **Load User Data**
    * Method: `POST`
    * URL: `/api/users/load`
    * Description: Loads all user data from the external dataset (https://dummyjson.com/users) into the in-memory H2 database.
    * Request Body: None
    * Response:
        * `200 OK:` Successfully loaded data.
        * \[Other appropriate status codes, e.g., `500 Internal Server Error` with an error message.]

### Retrieving Data

* **List Users (Free Text Search)**
    * Method: `GET`
    * URL: `/api/users`
    * Description: Retrieves a list of users based on a free text search across the `firstName`, `lastName`, and `ssn` fields.
    * Parameters:
        * `search` (query parameter, optional): The text to search for.
    * Response:
        * `200 OK:` Returns a list of users matching the search criteria.
        * \[Other appropriate status codes, e.g., `400 Bad Request` if the request is malformed.]
    * Example Response:

        \`\`\`json
        [
            {
                "id": 1,
                "firstName": "John",
                "lastName": "Doe",
                "email": "john.doe@example.com",
                "ssn": "xxx-xx-xxxx"
            },
            // ... more users
        ]
        \`\`\`

#   Frontend UI

##  Description

This is a frontend application built with ReactJS to implement a typeahead or auto-complete feature for searching users.

##  Details

* Question: Develop a frontend based upon ReactJS/AngularJS to implement typeahead or auto-complete feature on the web UI.

##  Technology Stack

* Frontend Framework: ReactJS
* State Management: \[Specify, e.g., React Context, Redux, etc.]
* UI Library: \[Specify, e.g., Material UI, Chakra UI, etc.]
* Testing: \[Specify, e.g., Jest, React Testing Library, etc.]
* Build Tool: \[Specify, e.g., Webpack, Vite, etc.]

##  Prerequisites

* Node.js \[Version]
* npm \[Version] or Yarn \[Version]
* A suitable IDE (e.g., VS Code)

##  Getting Started

### 1\. Project Setup

* \[Provide instructions on how to clone the repository, if applicable, or how to create a new project.]
* Example:

    1.  Clone the repository:

        \`\`\`bash
        git clone <repository\_url>
        \`\`\`

    2.  Navigate to the project directory:

        \`\`\`bash
        cd <project\_directory>
        \`\`\`

    3.  Install the dependencies:

        \`\`\`bash
        npm install
        \`\`\`

        or

        \`\`\`bash
        yarn install
        \`\`\`

### 2\. Configuration

* The application uses externalized configuration.
* [Explain how to configure environment-specific settings.  Specify any configuration parameters, such as:]
    * Backend API URL
* Example:
    *Create a `.env` file in the project root.*

    \`\`\`
    REACT_APP_API_BASE_URL=http://localhost:8080/api
    \`\`\`

### 3\. Running the Application

* \[Provide detailed instructions on how to run the application.]
* Example:

    1.  Start the development server:

        \`\`\`bash
        npm start
        \`\`\`

        or

        \`\`\`bash
        yarn start
        \`\`\`

    2.  Open your browser and navigate to `http://localhost:3000` (or the appropriate URL).

##  Key Features

* Typeahead/auto-complete search bar in the header section.
* Search functionality based on user's first name, last name, and/or SSN.
* Frontend app calls the backend API after entering the first 3 characters.
* Results are displayed in a dropdown below the search bar.
* Dropdown displays user attributes: id, firstName, lastName, ssn, and email.
* Navigation to a user details page upon clicking a dropdown item.
* User image is rendered on the details page.
* Single-page application (SPA) design.
* Responsive design.
* Lazy loading (as applicable).

**To get the complete working code for both the frontend and backend parts of this application with proper documentation, please contact:**

* Email: [saurabhdubey097@gmail.com](mailto:saurabhdubey097@gmail.com)
* WhatsApp: +7080778440
