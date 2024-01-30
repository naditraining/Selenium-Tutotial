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

### Java project structure

      MyJavaProject
      |-- src (default package)
      |   `-- com
      |       `-- mycompany
      |           `-- mypackage
      |               `-- Main.java (class name)
      |-- target 
      |-- README.md (optional)
      |-- .gitignore (optional)
      |-- build.xml (for Ant build tool, optional)
      |-- pom.xml (for Maven build tool, optional)

### java naming conventions
      Project names should be in uppercase letters.
      Package names should be in lowercase letters.
      Class and interface names should be in camel case, starting with an uppercase letter.
      Variable names should be in camel case, starting with a lowercase letter.
      Constant variables should be in uppercase letters with underscores separating words.
            final int MAX_SIZE = 100;
      Method names should be in camel case, starting with a lowercase letter.


### Structure of JAVA program

1. Documentation Section
2. Package Statement
3. Import Statements
4. Interface Statement
5. Class Definition
6. Main Method Class
    1. Main Method Definition
       
![Screenshot 2024-01-26 at 7 46 35 PM](https://github.com/naditraining/Selenium-Tutotial/assets/157560787/d3ea6726-394e-4766-a668-4ad425ed071e)

### Syntax
#### Variable declaration
      <Data-Type> <Variable Name> or <Data-Type> <Variable Name> = value;

      example:

      int var=100;
      int g;
      char c,d; // declaring more than one variable in a statement

#### Comments
      // Single line comment

      /* Multiline comment
      in Java */ 
#### Method syntax

      access-modifier return-type method-name(arguments)
      {
            //code goes here   
            return returnData; //optional when the return-type is void.
      }
      
      public static int addNumbers(int num1, int num2) {
              int sum = num1 + num2;
              return sum;
      }

Note: return type will be void when method is not returning anything.

### Data types
#### Primitive data type

Primitive data types are the most basic data types provided by the language. They represent simple values, and they are not objects

1. **byte:**
- Size: 8 bits
- Range: -128 to 127

byte myByte = 42;


2. **short:**
- Size: 16 bits
- Range: -32,768 to 32,767

short myShort = 1000;


3. **int:**
- Size: 32 bits
    - Range: -2^31 to 2^31-1

int myInt = 123456;


4. **long:**
- Size: 64 bits
    - Range: -2^63 to 2^63-1

long myLong = 9876543210L; // Note the 'L' at the end to indicate it's a long literal


5. **float:**
- Size: 32 bits
    - Example:

float myFloat = 3.14f; // Note the 'f' at the end to indicate it's a float literal

6. **double:**
- Size: 64 bits
    - Example:

double myDouble = 3.141592653589793;


7. **char:**
- Size: 16 bits
    - Represents a single character using single quotes

char myChar = 'A';


8. **boolean:**
- Represents true or false values

boolean myBoolean = true;
         
#### Reference data type

SUGGESTION - Please refer reference datatype after learning about - obects in java and how to create.

In Java, non-primitive data types, also known as reference types, are types that are derived from the primitive types. Unlike primitive types, these types are not simple values, but they are objects or instances of classes. Non-primitive data types include:

1. **Strings:** Strings are sequences of characters and are represented by the `String` class in Java.

   ```java
   String myString = "Hello, World!";
   ```

These non-primitive data types are more complex than primitive types and are used to model and work with more intricate data structures and behaviors in Java programs. They are created based on classes and interfaces, providing a higher level of abstraction and functionality compared to the simple values represented by primitive types.

2. **Classes:** Objects created from classes fall under non-primitive data types. A class is a blueprint for creating objects with fields (variables) and methods (functions).

   ```java
   class MyClass {
       // class members (fields and methods)
   }

   MyClass myObject = new MyClass();
   ```

3. **Arrays:** Arrays are objects that can store multiple values of the same type in a contiguous memory location.

   ```java
   int[] myArray = {1, 2, 3, 4, 5};
   ```

4. **Interfaces:** Interfaces define a contract for classes to implement. Objects can be created from classes that implement these interfaces.

   ```java
   interface MyInterface {
       // interface members
   }

   class MyImplementation implements MyInterface {
       // class members implementing the interface
   }

   MyInterface myObject = new MyImplementation();
   ```

5. **Enumerations (Enums):** Enums are a special type of class used to represent a fixed set of constants.

   ```java
   enum Days {
       MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY
   }

   Days today = Days.MONDAY;
   ```

### Keywords 

important keywords to know:

break, continue -  these two used to control the flow inside looping statements.

          
### Operators	
#### Arithmetic operators

      `+` (Addition):
      
      int result = 5 + 3; // result is 8
      System.out.println("result is "+result);
      
      `-` (Subtraction):
      
      int result2 = 7 - 4; // result is 3
      System.out.println("result2 is "+result2);
      
      
      `*` (Multiplication):
      
      int result3 = 6 * 2; // result is 12
      
      
      `/` (Division):
      
      int result4 = 10 / 2; // result is 5
      
      
      `%` (Modulus - Remainder):
      
      int result5 = 15 % 4; // result is 3
      
      
#### Logical operators	
      
      `==` (Equal to):
      
      boolean isEqual = (5 == 5); // isEqual is true
      
      
      `!=` (Not equal to):
      
      boolean isNotEqual = (7 != 5); // isNotEqual is true
      
      
      `>` (Greater than):
      
      boolean isGreaterThan = (8 > 5); // isGreaterThan is true
      
      
      `<` (Less than):
      
      boolean isLessThan = (3 < 6); // isLessThan is true
      
      
      `>=` (Greater than or equal to):
      
      boolean isGreaterOrEqual = (10 >= 10); // isGreaterOrEqual is true
      
      
      `<=` (Less than or equal to):
      
      boolean isLessOrEqual = (4 <= 5); // isLessOrEqual is true
      
#### Logical operators
      
      `&&` (Logical AND):
      
      boolean result7 = (true && false); // result is false
      
      
      `||` (Logical OR):
      
      boolean result8 = (true || false); // result is true
      
      
      `!` (Logical NOT):
      
      boolean result9 = !true; // result is false
      
#### Assignment Operators:
      
      `= ` (Assignment):
      
      int x = 5; // Assigns the value 5 to variable x
      
      
       `+=` (Add and assign):
      
      int y = 3;
      y += 2; // Equivalent to x = x + 2; // x is now 5
      
      
       `-=` (Subtract and assign):
      
      int z = 7;
      z -= 3; // Equivalent to x = x - 3; // x is now 4
      
#### Increment and Decrement Operators:
      
      `++` (Increment):
      
      int count = 5;
      count++; // Equivalent to count = count + 1; // count is now 6
      
      
      `--` (Decrement):
      
      int count1 = 8;
      count1--; // Equivalent to count = count - 1; // count is now 7
      
#### Conditional (Ternary) Operator:
      
      `? :` (Conditional):
      
      int number = 12;
      String result12 = (number % 2 == 0) ? "Even" : "Odd";
      // result is "Even" since 12 is divisible by 2
              
### Object	
      
      - Object Creation, Reference, Reference Variables	
      
      Object is a instance of class. Object hold data (variables) and behavior (methods) related to that entity.
      so only, objects are created to access the variables and methods of a particular class.
      
      'new' keyword is used to create object like below

      Car cr = new Car();
      Where Car - Class & cr - object name

      the object 'cr' in this example will hold the reference to all the variables and methods in the 'Car' class.
      
### Constructors	
      In Java, a constructor is a special method that is called when an object is created. It has the same name as the class and does not         have a return type, not even void. The primary purpose of a constructor is to initialize the instance variables of an object or             perform any other setup that is needed when an object is created.

      public class Car {
      
          // Instance variables
          String brand;
          String model;
          int year;
      
          // Constructor
          public Car(String brand, String model, int year) {
              this.brand = brand;
              this.model = model;
              this.year = year;
          }
      
          // Method to display car information
          public void displayInfo() {
              System.out.println("Brand: " + brand);
              System.out.println("Model: " + model);
              System.out.println("Year: " + year);
          }
      
          public static void main(String[] args) {
              // Creating an object of the Car class and invoking the constructor
              Car myCar = new Car("Toyota", "Camry", 2022);
      
              // Invoking a method to display car information
              myCar.displayInfo();
          }
      }

### Access Specifiers	

      Here is a table that summarizes the Java access specifiers along with their accessibility and usage:
      
      | Access Specifier | Class | Package | Subclass | World |
      | ---------------- | ----- | ------- | -------- | ----- |
      | `public`         | Yes   | Yes     | Yes      | Yes   |
      | `protected`      | Yes   | Yes     | Yes      | No    |
      | `default`        | Yes   | Yes     | No       | No    |
      | `private`        | Yes   | No      | No       | No    |
      
      - **`public`**:
        - Accessible from anywhere. There are no restrictions on its access.
        - Example: `public class MyClass { }`
      
      - **`protected`**:
        - Accessible within the same class, same package, and subclasses. Outside the package, it is not accessible.
        - Example: `protected int myVariable;`
      
      - **`default`** (no modifier):
        - Accessible within the same class and same package. Outside the package, it is not accessible.
        - Example: `int myVariable;`
      
      - **`private`**:
        - Accessible only within the same class. Not accessible from subclasses or other packages.
        - Example: `private String myField;`

      Please note that these access specifiers apply to classes, methods, and fields in Java. They control the visibility and accessibility       of these elements within your codebase.
      
### Debugging in Eclipse IDE	    
