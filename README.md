# Cloud-Enabled-Deployment-with-GCP

This guide provides step-by-step instructions for setting up and running the frontend application, running backend microservices, and updating configuration files for Google Cloud Platform (GCP) deployment.

---
## Student Information

- **Name:** Thesandu Thathsara
- **Student Registration Number:** 2301671131
- **Email Address:** thesandu1602500@gmail.com
---

## How This Project Works: Video Overview

Watch the following video for an explanation of how the Cloud-Enabled-Deployment-with-GCP project works:

[How This Project Works - Cloud-Enabled Deployment Demo](https://drive.google.com/file/d/1dojebb8l0mBWqLl6GZ2RBv3G9NmErdzb/view?usp=drive_link)

---

## 1. Backend Microservices: Setup & Run

### Prerequisites
- Java 11+
- Maven

### Build and Run Services Locally

For each microservice (`course-service`, `media-service`, `student-service`):

```sh
cd <service-name>
mvn clean install
mvn spring-boot:run
```

> Each service will start on its configured port (see `application.properties` in each service).

---

## 2. application-gcp.properties Changes

To deploy backend services on GCP, update the `application-gcp.properties` file with your GCP-specific settings.

**Typical changes include:**
- GCP Cloud SQL instance details
- Credentials and connection strings

**Example:**

```properties
spring.datasource.host= <The public IP address of your Cloud SQL instance>
spring.datasource.port= <The port your MySQL instance listens on (default: 3306)>
spring.datasource.url= <Add your Public IP address>
spring.datasource.username= <Your Cloud SQL username>
spring.datasource.password= <Your Cloud SQL password>
```

**How to use GCP profile:**
```sh
mvn spring-boot:run -Dspring-boot.run.profiles=gcp
```

---

## 3. Frontend App: Setup & Run

### Prerequisites
- Node.js (v16+ recommended)
- npm or yarn

### Steps

#### a. Navigate to Frontend Directory
```sh
cd frontend-app
```

#### b. Install Dependencies
```sh
npm install
# or
yarn install
```
