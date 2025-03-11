#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |


### What is settings.xml
- The Maven settings.xml file is commonly used to define the local repository location, alternate remote repository servers, and authentication information for private repositories.
For example:
- Nexus username and password can be declared within the <server> tag inside the settings.xml.
### settings.xml location

- Maven can utilize two settings.xml files simultaneously:
- Maven installation directory:
- $M2_HOME/conf/settings.xml (global settings)
- User's home directory:
- ${user.home}/.m2/settings.xml (user settings)
- Both files are optional. If both files are present, the values in the user home settings file override the values from the global settings file.

----
### Types of Maven Repository
- A Maven repository is a directory containing packaged JAR files along with their corresponding pom.xml files.
- Maven searches for dependencies in these repositories.
- There are three types of Maven repositories:
### Local Repository:
 - This repository is on the developer's local machine and stores all dependencies that have been downloaded.
### Central Repository:
 - The default repository used by Maven, maintained by the Maven community. It contains a vast number of commonly used libraries.
### Remote Repository:
 - Any other repository accessed over the network, typically used for sharing internal or proprietary libraries across a team or organization.

![ Types of Maven Repository- Tech World with Murali - Moole Muralidhara Reddy.png](https://github.com/techworldwithmurali/devops-zero-to-hero/blob/main/Day-9/images/Day%20%208-%20%20Types%20of%20Maven%20Repository-%20Moole%20Muralidhara%20Reddy%20-%20Tech%20World%20with%20Murali.png)
