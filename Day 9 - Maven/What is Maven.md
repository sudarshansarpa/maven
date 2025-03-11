#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |


### What is a Build Tool?  

A build tool is software used to automate the process of converting source code into executable applications. This process includes compiling, linking, and packaging the code into a usable or deployable format (e.g., `.jar` for Java applications).  

### Types of Build Tools  

There are various types of build tools available in DevOps, each catering to different languages and environments. The most common ones include:  

- **Apache Ant** – A Java-based build tool that uses XML configuration files.  
- **Maven** – A widely used Java-based build automation tool that simplifies project management.  
- **Gradle** – A modern build tool that supports Java, Kotlin, and Groovy, offering improved performance and flexibility.  

---

## What is Maven?  

- Maven is an open-source build automation and project management tool, primarily used for Java-based applications.
- It simplifies the build process and ensures consistency across projects by managing dependencies, compiling source code, running tests, packaging applications, and deploying artifacts.  

### Key Features of Maven  

#### 1. **Dependency Management**  
Maven automatically downloads project dependencies from remote repositories such as the [Maven Central Repository](https://mvnrepository.com/), ensuring that the correct versions are used. Dependencies are managed in the `pom.xml` file.  

#### 2. **Build Lifecycle**  
Maven follows a defined lifecycle consisting of several phases:  
- **Validate** – Ensures all necessary information is available.  
- **Compile** – Compiles the source code.  
- **Test** – Runs unit tests.  
- **Package** – Packages the compiled code into JAR, WAR, or EAR files.  
- **Verify** – Performs integration testing.  
- **Install** – Installs the package locally for further use.  
- **Deploy** – Deploys the packaged application to a remote repository.  

#### 3. **Plugins and Extensibility**  
Maven is highly extensible through plugins. Common plugins include:  
- **maven-compiler-plugin** (for compiling Java code)  
- **maven-surefire-plugin** (for running unit tests)  
- **maven-deploy-plugin** (for deploying artifacts)  

#### 4. **Project Object Model (POM.xml)**  
Maven uses a configuration file called `pom.xml` to define:  
- Project details (name, version, description)  
- Dependencies and their versions  
- Plugins and their configurations  
- Build and packaging instructions  

#### 5. **Uploading Artifacts to Remote Repositories**  
Maven allows uploading of build artifacts (JAR, WAR files) to remote repositories such as:  
- **Maven Central Repository**  
- **Nexus Repository Manager**  
- **JFrog Artifactory**  
