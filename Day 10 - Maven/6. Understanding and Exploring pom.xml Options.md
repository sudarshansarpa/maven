## Understanding and Exploring pom.xml Options

### **Best Practices in Maven POM for Spring Boot Projects**
**Description:**  
- This Maven POM file follows **best practices** for managing a Spring Boot project with **multi-module support, structured dependencies, and automated build processes**.
- It includes essential **Spring Boot starters, MySQL database integration, Maven build plugins, and profile-based configurations** for different environments. Additionally, it supports **code coverage analysis using Jacoco and repository management with Nexus**.

**"The `pom.xml` file is available here: [link](https://github.com/techworldwithmurali/devops-zero-to-hero/blob/main/Day%2010%20-%20Maven/pom.xml)."**

## 1. **Root Element: `<project>`**
```xml
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
```
- This defines the **POM file format** and XML schema.
- The `xmlns` and `xsi:schemaLocation` ensure compliance with **Maven’s standard schema**.

---

## 2. **Model Version**
```xml
<modelVersion>4.0.0</modelVersion>
```
- Specifies **Maven’s POM model version**.
- The value **4.0.0** is mandatory for Maven 2, 3, and 4.

---

## 3. **Project Metadata**
```xml
<groupId>com.techworldwithmurali</groupId>
<artifactId>user-registration</artifactId>
<version>0.0.1-SNAPSHOT</version>
<packaging>jar</packaging>
```
- **`groupId`**: Identifies the **project's organization** (e.g., `com.techworldwithmurali`).
- **`artifactId`**: The **name of the project** (`user-registration`).
- **`version`**: Project version (`0.0.1-SNAPSHOT`).
- **`packaging`**: Type of build output (`jar`).

---

## 4. **Parent Project (Spring Boot Starter Parent)**
```xml
<parent>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-parent</artifactId>
    <version>3.3.4</version>
    <relativePath/> <!-- Lookup parent from repository -->
</parent>
```
- Inherits common dependencies and configurations from **Spring Boot Starter Parent**.
- Helps in version management of dependencies.

---

## 5. **Multi-Module Configuration**
```xml
<modules>
    <module>user-service</module>
    <module>order-service</module>
    <module>payment-service</module>
</modules>
```
- Defines a **multi-module Maven project**.
- The parent `POM` manages multiple child modules: **user-service, order-service, and payment-service**.

---

## 6. **Project Properties**
```xml
<properties>
    <maven.compiler.source>17</maven.compiler.source>
    <maven.compiler.target>17</maven.compiler.target>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
</properties>
```
- **`maven.compiler.source/target`**: Defines Java version **17** for compilation.
- **`project.build.sourceEncoding`**: Sets encoding to **UTF-8**.

---

## 7. **Dependencies**
### Spring Boot Dependencies
```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter</artifactId>
</dependency>
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-actuator</artifactId>
</dependency>
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-data-jpa</artifactId>
</dependency>
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
</dependency>
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-thymeleaf</artifactId>
</dependency>
```
- **`spring-boot-starter`**: Core dependency for Spring Boot.
- **`spring-boot-starter-actuator`**: Provides monitoring and health checks.
- **`spring-boot-starter-data-jpa`**: Enables ORM using **Hibernate**.
- **`spring-boot-starter-web`**: Adds **Spring MVC** for REST API development.
- **`spring-boot-starter-thymeleaf`**: Adds **Thymeleaf** template engine for web applications.

### Database Dependency (MySQL)
```xml
<dependency>
    <groupId>mysql</groupId>
    <artifactId>mysql-connector-java</artifactId>
    <version>8.0.33</version>
</dependency>
```
- Provides the **MySQL JDBC driver** for database connectivity.

### Testing Dependencies
```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-test</artifactId>
    <scope>test</scope>
</dependency>
```
- Provides **JUnit and Mockito** for unit testing.

---

## 8. **Distribution Management (Nexus Repository)**
```xml
<distributionManagement>
    <snapshotRepository>
        <id>nexus-snapshots</id>
        <url>https://nexus.techworldwithmurali.in/repository/maven-snapshots/</url>
    </snapshotRepository>
    <repository>
        <id>nexus-releases</id>
        <url>https://nexus.techworldwithmurali.in/repository/maven-releases/</url>
    </repository>
</distributionManagement>
```
- Defines **repositories** to store artifacts:
  - **Snapshot Repository** for development versions.
  - **Release Repository** for stable versions.

---

## 9. **Build Configuration**
```xml
<build>
    <plugins>
 </plugins>
    </build>
```
### Spring Boot Maven Plugin
```xml
<plugin>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-maven-plugin</artifactId>
</plugin>
```
- Helps in **building executable JARs**.

### Jacoco Plugin (Code Coverage)
```xml
<plugin>
    <groupId>org.jacoco</groupId>
    <artifactId>jacoco-maven-plugin</artifactId>
    <version>0.8.10</version>
</plugin>
```
- **Generates test coverage reports**.

### Common Maven Plugins
```xml
<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-compiler-plugin</artifactId>
    <version>3.13.0</version>
    <configuration>
        <source>${maven.compiler.source}</source>
        <target>${maven.compiler.target}</target>
    </configuration>
</plugin>
```
- **Compiles Java source code**.

```xml
<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-surefire-plugin</artifactId>
    <version>3.2.5</version>
</plugin>
```
- **Runs unit tests**.

---

## 10. **Project Information**
```xml
<url>https://github.com/techworldwithmurali/user-registration</url>
```
- GitHub repository URL.

### Licensing
```xml
<licenses>
    <license>
        <name>Apache License 2.0</name>
        <url>https://www.apache.org/licenses/LICENSE-2.0</url>
    </license>
</licenses>
```
- Defines **Apache 2.0 License**.

### Developers
```xml
<developers>
    <developer>
        <id>murali</id>
        <name>Moole Muralidhara Reddy</name>
        <email>techworldwithmurali@gmail.com</email>
    </developer>
</developers>
```
- Lists **project maintainers**.

---

## 11. **Source Code Management (SCM)**
```xml
<scm>
    <connection>scm:git:https://github.com/techworldwithmurali/user-registration.git</connection>
    <developerConnection>scm:git:git@github.com:techworldwithmurali/user-registration.git</developerConnection>
</scm>
```
- Defines **GitHub repository details**.

---

## 12. **Profiles (Environment-Based Configuration)**
### Development Profile (Active by Default)
```xml
<profile>
    <id>dev</id>
    <activation>
        <activeByDefault>true</activeByDefault>
    </activation>
</profile>
```
- Default profile for **development**.

### Production Profile
```xml
<profile>
    <id>prod</id>
    <activation>
        <property>
            <name>env</name>
            <value>production</value>
        </property>
    </activation>
</profile>
```
- Used when `-Denv=production` is specified.
