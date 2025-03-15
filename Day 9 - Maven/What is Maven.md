#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |


### What is a Build Tool?  

- A **build tool** is software used to **automate** the process of converting source code into an **executable application**.  
- This process includes **compiling, linking, and packaging** the code into a deployable format (e.g., `.jar` for Java applications, `.exe` for Windows applications).  
- Build tools play a crucial role in software development by:  
1. **Managing Dependencies** – Handling external libraries and ensuring the correct versions are used.  
2. **Automating Repetitive Tasks** – Compiling code, running tests, packaging applications, and deploying software.  
3. **Ensuring Consistency** – Standardizing build processes across different environments to reduce errors.  

### Types of Build Tools  

Various build tools cater to different languages and environments. The most common ones include:  

- **Apache Ant** – A Java-based build tool that uses XML configuration files for task automation.  
- **Maven** – A popular Java-based build automation and project management tool that simplifies dependency management and follows a convention-over-configuration approach.  
- **Gradle** – A modern and flexible build tool supporting Java, Kotlin, and Groovy, known for its **performance optimizations** and **incremental builds**.  

## What is Maven?  

- Maven is an open-source build automation and project management tool, primarily used for Java-based applications.
- It simplifies the build process and ensures consistency across projects by managing dependencies, compiling source code, running tests, packaging applications, and deploying artifacts.
- Maven was developed by Apache Software Foundation.
- Maven is now maintained as an open-source project under the Apache License.

### Key Features of Maven  

#### 1. **Dependency Management**  
- Maven automatically downloads project dependencies from remote repositories such as the [Maven Central Repository](https://repo.maven.apache.org/maven2/), ensuring that the correct versions are used.
-  Dependencies are managed in the `pom.xml` file.  

#### 2. **Build Lifecycle**  
Maven follows a defined lifecycle consisting of several phases:  
- **Validate** – Ensures all necessary information is available.  
- **Compile** – Compiles the source code.  
- **Test** – Runs unit tests.  
- **Package** – Packages the compiled code into JAR, WAR, or EAR files.  
- **Verify** – runs unit tests + integration tests and ensures the build meets all required conditions.
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
