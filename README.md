# Selenium-Tutotial
## Introduction to automation testing
### Why Selenium 

      Selenium is an open-source suite of tools and libraries that is used for browser automation. Selenium is used to:
      
      It allows users to test their websites functionally on different browsers. 
      Perform Cross browser testing to check if the website functions consistently across different browsers. 
      It provides a single interface that lets you write test scripts in programming languages like Ruby, Java, NodeJS, PHP, Perl, Python, JavaScript, and C#, among others. Selenium 
      is very extensible and can be integrated with other tools and frameworks like TestNG, JUnit, Cucumber, etc.

![Screenshot 2024-01-26 at 7 32 16 PM](https://github.com/naditraining/Selenium-Tutotial/assets/157560787/7e8a3173-34dc-4bfc-b188-1f22eebd9978)

### Why we need to JAVA well before knowing much about automation

      Selenium is a library with readymade utility methods to automate the actions in web applications. To utilise this library, we have to learn a programming language first,
      so we can import the selenium library and use the readymade utilities to interact with the web application.
      

### Sample Selenium program execution

      Clone the project in Day 1 and import as maven project in IntelliJ to run the sample selenium script

### Required set up to start learning JAVA
    1: Language - Install Java Development Kit (JDK)
    2: IDE (Editor) - Install IntelliJ IDEA

## JAVA, Installation, Setting environment variable
### Java versions

https://www.oracle.com/au/java/technologies/downloads/archive/


### JAVA installation

Check if Java is Installed using below command

java -version

if java version is not returned, you can install java using below steps

visit here to download - https://www.oracle.com/java/technologies/javase/jdk11-archive-downloads.html

Things to consider before downloading
1. OS (windows, linux)
2. Processor architecture (x64, ARM)

Follow steps 
### Set JAVA_HOME Environment Variable
The steps vary for windows and Mac OS 
#### MAC OS 
1. Open Terminal.
2. Edit the shell profile file (e.g., ~/.bash_profile, ~/.zshrc, or ~/.bashrc) using a text editor like nano or vi. For example:
nano ~/.zshrc
3. Add the following line at the end to set the JAVA_HOME environment variable:
export JAVA_HOME=/path/to/your/jdk
note - Replace /path/to/your/jdk with the actual path to your JDK installation directory.
4. Save the file and exit the text editor.
5. Run the following command to apply the changes:
source ~/.zshrc

#### Windows
1. After installing the JDK, find the installation directory. By default, it is something like C:\Program Files\Java\jdk1.x.x
2. Right-click on the Windows icon (Start menu) and select "System."
3. Click on "Advanced system settings" on the left.
4. In the System Properties window, click the "Environment Variables..." button.
5. Under the "System variables" section, click "New."
6. Set the variable name as JAVA_HOME.
7. Set the variable value to the path of your JDK installation directory (e.g., C:\Program Files\Java\jdk1.x.x).
8. Click "OK" to close each of the windows.


  ##### Update Path Variable
  1. In the same "Environment Variables" window, find the "Path" variable under the "System variables" section and click "Edit."
  2. In the "Edit Environment Variable" window, click "New" and add the following two entries:
  %JAVA_HOME%\bin
  %JAVA_HOME%\jre\bin
  3. This allows your system to find the Java executables.
  4. Click "OK" to close each of the windows.
  
  
  ##### Verify Setup
  1. Open a new command prompt (cmd) or PowerShell window.
  2. Type the following commands to check if Java is installed and configured correctly:
  
  java -version


### JVM, JRE, JDK

![Screenshot 2024-01-26 at 7 13 29 PM](https://github.com/naditraining/Selenium-Tutotial/assets/157560787/b44d7870-6c1a-40e3-9b6d-97ae1bcbaa8e)

reference: https://medium.com/@shashane.ranasinghe/jdk-vs-jvm-vs-jre-92916faead34

### Structure of JAVA program

1. Documentation Section
2. Package Statement
3. Import Statements
4. Interface Statement
5. Class Definition
6. Main Method Class
    1. Main Method Definition
       
![Screenshot 2024-01-26 at 7 46 35 PM](https://github.com/naditraining/Selenium-Tutotial/assets/157560787/d3ea6726-394e-4766-a668-4ad425ed071e)

### Data types
    1. Primitive data type
    2. Reference data type

### Keywords, Identifiers, Expressions	
          
### Operators	
        - Arithmetic operators	
        - Logical operators	
        - Bitwise operators	
        - Assignment operators	
        - Relational operators	
          
### Variables	
        - Declaration, Definition, Types		
      
### Syntax, Types	
    
### Object	
      - Object Creation, Reference, Reference Variables	
      
### Constructors	
### Pass by value and Pass by reference	
### Access Specifiers	
      
### Debugging in Eclipse IDE	    
