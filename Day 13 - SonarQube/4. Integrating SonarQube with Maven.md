### **Integrating SonarQube with  Maven**  

#### **Prerequisites**  
1. Install **Java 11+** and set environment variables.  
2. Install **Apache Maven** and configure the path.  
3. Install **SonarQube** and up & running 
4. Generate an authentication token in sonarqube.  

---

### **Step 1: Clone the Repository**  
```sh
git clone https://github.com/techworldwithmurali/user-registration.git
```

---

### **Step 2: Add SonarQube Plugin to `pom.xml`**  
Add the SonarQube Scanner plugin inside `<build>`:  

```xml
<build>
    <plugins>
        <plugin>
            <groupId>org.sonarsource.scanner.maven</groupId>
            <artifactId>sonar-maven-plugin</artifactId>
            <version>3.10.0.2594</version>
        </plugin>
    </plugins>
</build>
```

---

### **Step 3: Add JaCoCo for Code Coverage**  
To ensure SonarQube detects code coverage, add JaCoCo inside `<build>`:  

```xml
<plugin>
    <groupId>org.jacoco</groupId>
    <artifactId>jacoco-maven-plugin</artifactId>
    <version>0.8.10</version>
    <executions>
        <execution>
            <id>prepare-agent</id>
            <goals>
                <goal>prepare-agent</goal>
            </goals>
        </execution>
        <execution>
            <id>report</id>
            <phase>verify</phase>
            <goals>
                <goal>report</goal>
            </goals>
        </execution>
    </executions>
</plugin>
```

---

### **Step 4: Run Tests & Generate Code Coverage**  
Run:  
```sh
mvn clean verify
```
👉 This will generate:  
- Test execution results  
- JaCoCo coverage report at **`target/site/jacoco/jacoco.xml`**  

---

### **Step 5: Run SonarQube Analysis**  
Execute:  

```sh
mvn sonar:sonar \
    -Dsonar.projectKey=my-project \
    -Dsonar.host.url=http://localhost:9000 \
    -Dsonar.login=your-sonarqube-token
```

#### **Example:**  
```sh
mvn sonar:sonar \
    -Dsonar.projectKey=user-registration \
    -Dsonar.host.url=https://sonarqube.techworldwithmurali.in \
    -Dsonar.login=400556b03e5e8664cd9d7ff0010fbab75373c3b5
```

🔹 **Note:** If SonarQube authentication is enabled, generate a token under **User → My Account → Security**.  

---

### **Step 6: Verify SonarQube Dashboard**  
Open https://sonarqube.techworldwithmurali.in in your browser.  
Check if the project is listed with:  
✅ Code Smells  
✅ Bugs  
✅ Vulnerabilities  
✅ Code Coverage  

---

🎉 **Congratulations!** You have successfully integrated SonarQube with Maven and generated the report. 🚀
