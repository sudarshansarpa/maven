### Types of Maven Repository

In **Maven**, repositories are used to store dependencies, plugins, and other artifacts. There are three main types of repositories:

### 1. **Local Repository**
   - The **local repository** is a directory on your computer where Maven stores downloaded dependencies and artifacts.
   - Default location:  
     ```
     ~/.m2/repository (Linux/Mac)
     C:\Users\<username>\.m2\repository (Windows)
     ```
   - **Purpose:**
     - Stores dependencies downloaded from remote repositories.
     - Avoids re-downloading dependencies if they are already present.
   - **Example:**
     - When you run `mvn install`, your project's built artifacts are stored in the local repository.
     - If you add a dependency in `pom.xml`, Maven first checks the local repository before downloading from a remote repository.

---

### 2. **Central Repository**
   - The **central repository** is a publicly available repository maintained by Maven at **[Maven Central](https://repo.maven.apache.org/maven2/)**.
   - **Purpose:**
     - Provides a standard location to download commonly used dependencies.
     - Automatically accessed when dependencies are not found in the local repository.
   - **Example:**
     - If you add a dependency for **Spring Boot**, Maven will fetch it from the central repository:
       ```xml
       <dependency>
           <groupId>org.springframework.boot</groupId>
           <artifactId>spring-boot-starter-web</artifactId>
           <version>3.2.1</version>
       </dependency>
       ```
     - If the dependency is not in your local repository, it gets downloaded from the central repository.

---

### 3. **Remote Repository**
   - A **remote repository** is a repository hosted on a server (public or private) that Maven can access over the network.
   - **Types:**
     1. **Maven Central Repository** (default remote repository).
     2. **Company-Specific Remote Repository** (e.g., Nexus, Artifactory) for storing internal dependencies.
   - **Purpose:**
     - Provides additional dependencies that are not in Maven Central.
     - Used by organizations to host private artifacts.
   - **Example:**
     - If your company maintains internal libraries, they can be hosted in **Nexus** or **Artifactory**.
     - To use a custom remote repository, add it to `pom.xml`:
       ```xml
       <repositories>
           <repository>
               <id>my-company-repo</id>
               <url>https://repo.techworldwithmurali.com/maven2/</url>
           </repository>
       </repositories>
       ```
     - Maven will check this remote repository if the dependency is not found locally or in the central repository.

---

Maven searches for the dependencies in the following order:

### Local Repository
First, Maven checks the **local repository** (`~/.m2/repository`) to see if the required dependency is already downloaded.

### Central Repository
If the dependency is not found locally, Maven queries the **Maven Central Repository** (`https://repo.maven.apache.org/maven2/`) to download it.

### Remote Repository
If the dependency is not in the central repository, Maven looks for any **custom remote repositories** configured in the `pom.xml` or `settings.xml`.
- This could be **private repositories** like **Nexus, Artifactory**, or other third-party repositories.

### Failure
If Maven **cannot find** the dependency in any of these repositories, it **throws an error** and stops the build.



### **Summary Table**

| Repository Type   | Location | Purpose |
|------------------|----------|---------|
| **Local**  | Developer's machine (`~/.m2/repository`) | Caches dependencies to avoid re-downloading |
| **Central** | Public repository (`repo.maven.apache.org`) | Provides widely used dependencies |
| **Remote**  | Custom-hosted (e.g., Nexus, Artifactory) | Stores company-specific or third-party dependencies |
