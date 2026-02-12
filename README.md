# Nexus Project & Buy-02 Microservices

This repository contains the infrastructure and source code for the **Buy-02 E-commerce Application**, a microservices-based architecture managed by a **Nexus Repository Manager**.

## Setup

### Prerequisites
*   **Docker** & **Docker Compose**
*   **Java 17+**
*   **Maven 3.8+**

### Installation
1.  **Clone the repository**:
    ```bash
    git clone https://github.com/nicgen/nexus.git
    cd nexus
    ```

2.  **Start the Infrastructure**:
    Deploy Nexus, Jenkins, and Traefik using Docker Compose:
    ```bash
    docker-compose up -d
    ```

3.  **Access Services**:
    *   **Nexus**: `http://nexus.local.hello-there.net` (Admin: `admin` / *configured_password*)
    *   **Jenkins**: `http://jenkins.local.hello-there.net`
    *   **Traefik Dashboard**: `http://traefik.local.hello-there.net`

## Configuration

### Nexus Repository Manager
The Nexus instance is pre-configured with the following repositories:
*   **maven-releases**: Stores stable artifacts (release versions).
*   **maven-snapshots**: Stores development artifacts (`-SNAPSHOT`).
*   **maven-public**: A group repository aggregating the above + Maven Central.
*   **docker-hosted**: A private Docker registry (Port `8082`).

### Security Realms
To enable Docker interactions, the **Docker Bearer Token Realm** must be active in Nexus:
1.  Go to **Server Administration** -> **Security** -> **Realms**.
2.  Add **Docker Bearer Token Realm** to the Active list.
3.  Save.

### Jenkins Pipeline
The `buy-02/Jenkinsfile` defines the CI/CD process:
*   **Build**: Compiles Java code.
*   **Test**: Runs Unit Tests.
*   **Analyze**: Scans with SonarQube.
*   **Publish**: Deploys JARs to Nexus (`mvn deploy`).
*   **Dockerize**: Pushes Docker images to Nexus Registry.

## Usage

### Developing with Nexus
To build the project and resolve dependencies from your local Nexus:
1.  Ensure your `~/.m2/settings.xml` (or project `settings.xml`) points to `http://nexus.local.hello-there.net/repository/maven-public/`.
2.  Run the build:
    ```bash
    cd buy-02
    mvn clean deploy
    ```

### Running the Application
The `buy-02` application consists of 4 services. You can run them via the main docker-compose or individually:
```bash
cd buy-02
docker-compose up -d --build
```
Access the frontend at `http://app.local.hello-there.net`.

## Documentation
*   [Audit Guide](AUDIT_GUIDE.md): Detailed compliance audit.
*   [Architecture Walkthrough](walkthrough.md): Technical deep-dive.
