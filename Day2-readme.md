### Static in Java

  In Java, the `static` keyword is used to declare members (fields, methods, and nested classes) that belong to the class rather than 
  instances of the class. Here's the purpose and an example of using `static` in Java:
  
  1. **Static Fields (Class Variables):**
     - **Purpose:** A static field is shared among all instances of a class. It belongs to the class rather than a specific object.
     - **Example:**
       ```java
       public class ExampleClass {
           // Static field
           static int staticField = 0;
  
           // Other instance fields
           int instanceField;
  
           // Constructor
           public ExampleClass(int instanceField) {
               this.instanceField = instanceField;
               // Accessing static field within the constructor
               staticField++;
           }
       }
       ```
  
  2. **Static Methods:**
     - **Purpose:** A static method belongs to the class rather than an instance. It can be called using the class name without creating an 
  object of the class.
     - **Example:**
       ```java
       public class MathUtils {
           // Static method to calculate the square of a number
           public static int square(int num) {
               return num * num;
           }
       }
  
       // Usage
       int result = MathUtils.square(5);
       ```
  
  3. **Static Blocks:**
     - **Purpose:** A static block is used to initialize static fields or perform one-time actions when the class is loaded.
     - **Example:**
       ```java
       public class StaticBlockExample {
           // Static field
           static int staticField;
  
           // Static block
           static {
               // Initialization in a static block
               staticField = 42;
               System.out.println("Static block executed");
           }
       }
       ```
  
  4. **Static Nested Classes:**
     - **Purpose:** A static nested class is associated with its outer class rather than an instance of the outer class.
     - **Example:**
       ```java
       public class OuterClass {
           // Static nested class
           static class StaticNestedClass {
               void display() {
                   System.out.println("Inside static nested class");
               }
           }
       }
  
       // Usage
       OuterClass.StaticNestedClass nestedObj = new OuterClass.StaticNestedClass();
       nestedObj.display();
       ```
  
  5. **Static Import:**
     - **Purpose:** Allows you to use static members of a class without specifying the class name.
     - **Example:**
       ```java
       import static java.lang.Math.*;
  
       public class StaticImportExample {
           public static void main(String[] args) {
               // Using static members without the Math class prefix
               double result = sqrt(25.0);
               System.out.println(result);
           }
       }
       ```
  
  It's important to note that `static` members are associated with the class itself and not with instances of the class. They are loaded 
  into memory when the class is loaded and can be accessed using the class name.

### Constructors 

  In Java, a constructor is a special type of method that is used to initialize objects. It has the same name as the class to which it 
  belongs and is called when an object of the class is created. The purpose of a constructor is to set up the initial state of an object by 
  assigning values to its instance variables or performing other necessary setup tasks.
  
  Certainly! If you want to create a constructor with parameters in a Selenium class, you can pass the necessary information, such as the browser type and URL, during object creation. Here's an example:

```java
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.firefox.FirefoxDriver;

public class SeleniumExampleWithParameters {
    // WebDriver instance as an instance variable
    private WebDriver driver;

    // Constructor with parameters
    public SeleniumExampleWithParameters(String browserType, String url) {
        if (browserType.equalsIgnoreCase("chrome")) {
            // Set the path to your ChromeDriver executable
            System.setProperty("webdriver.chrome.driver", "path/to/chromedriver");
            this.driver = new ChromeDriver();
        } else if (browserType.equalsIgnoreCase("firefox")) {
            // Set the path to your GeckoDriver executable
            System.setProperty("webdriver.gecko.driver", "path/to/geckodriver");
            this.driver = new FirefoxDriver();
        } else {
            throw new IllegalArgumentException("Unsupported browser type: " + browserType);
        }

        // Navigate to the specified URL
        driver.get(url);
    }

    // Method to perform some Selenium actions
    public void performSeleniumActions() {
        // Perform Selenium actions...

        // Close the browser
        driver.quit();
    }

    public static void main(String[] args) {
        // Creating an object of SeleniumExampleWithParameters with browser type and URL parameters
        SeleniumExampleWithParameters seleniumExample =
                new SeleniumExampleWithParameters("chrome", "https://www.example.com");

        // Perform Selenium actions
        seleniumExample.performSeleniumActions();
    }
  }
  ```
  
  In this example:
  
  - The `SeleniumExampleWithParameters` class has a constructor that takes two parameters: `browserType` and `url`.
  - The constructor initializes the `WebDriver` instance based on the provided `browserType` (either "chrome" or "firefox"). Make sure to 
  set the paths to your ChromeDriver and GeckoDriver executables accordingly.
  - The constructor navigates to the specified URL.
  - The `performSeleniumActions` method demonstrates where you might perform other Selenium actions.
  - In the `main` method, an object of `SeleniumExampleWithParameters` is created by passing the desired browser type and URL.
  
  You can customize this class further based on your requirements, such as adding more parameters or additional Selenium configurations.
  
  Constructors are essential for ensuring that objects are properly initialized when they are created, and they contribute to the concept of 
  encapsulation in object-oriented programming by allowing you to control the initial state of objects.

### Inheritance 

  Inheritance is a fundamental concept in object-oriented programming (OOP) that allows a class (subclass or child class) to use       
  variables and methods from another class (superclass or parent class). In Selenium automation testing with Java, inheritance can be 
  used to create reusable and maintainable code by extending and customizing existing classes. Let's explore an example using inheritance 
  in a Selenium framework:

  Note: this example demonstrates single inheritance type
  
  Suppose you have a `BaseTest` class that sets up the WebDriver instance and provides common methods used across multiple test classes:
  
  ```java
  import org.openqa.selenium.WebDriver;
  import org.openqa.selenium.chrome.ChromeDriver;
  
  public class BaseTest {
      // WebDriver instance
      protected WebDriver driver;
  
      // Constructor to initialize WebDriver
      public BaseTest() {
          // Set the path to your ChromeDriver executable
          System.setProperty("webdriver.chrome.driver", "path/to/chromedriver");
          // Initialize ChromeDriver
          this.driver = new ChromeDriver();
      }
  
      // Common method to navigate to a URL
      protected void navigateToUrl(String url) {
          driver.get(url);
      }
  
      // Common method to close the browser
      protected void closeBrowser() {
          driver.quit();
      }
  }
  ```
  
  Now, you can create a specific test class, let's say `LoginTest`, that inherits from `BaseTest`:
  
  ```java
  public class LoginTest extends BaseTest {
  
      // Test method for login functionality
      public void testLogin() {
          // Use inherited methods and properties
          navigateToUrl("https://www.example.com/login");
  
          // Perform login actions using driver
  
          // Example assertion
          // assertTrue(driver.findElement(By.id("logoutButton")).isDisplayed());
  
          // Close the browser using the inherited method
          closeBrowser();
      }
  
      public static void main(String[] args) {
          // Create an object of LoginTest and run the test
          LoginTest loginTest = new LoginTest();
          loginTest.testLogin();
      }
  }
  ```
  
  In this example:
  
  - The `BaseTest` class provides common setup and utility methods for Selenium tests.
  - The `LoginTest` class inherits from `BaseTest` using the `extends` keyword, which means it inherits the `driver`, `navigateToUrl`, and     `closeBrowser` methods.
  - The `LoginTest` class can use these inherited methods in its own test methods, focusing only on the specific behavior related to the 
   login functionality.
  
  This approach promotes code reuse, as the common setup and utility methods are defined in the base class, and specific test classes only    need to focus on the unique aspects of their functionality. It makes the code more modular, maintainable, and reduces redundancy.

  #### Multi level inheritance in Java

    Multi-level inheritance in Java occurs when a class extends another class, and then another class extends the second class. In Selenium 
    automation testing, you might organize your code in a way that multiple classes are involved in creating a hierarchy. Here's an example 
    with multi-level inheritance:
  
    Suppose you have a `BaseTest` class that initializes the WebDriver and provides common methods:
    
    
      import org.openqa.selenium.WebDriver;
      import org.openqa.selenium.chrome.ChromeDriver;
      
      public class BaseTest {
          // WebDriver instance
          protected WebDriver driver;
      
          // Constructor to initialize WebDriver
          public BaseTest() {
              // Set the path to your ChromeDriver executable
              System.setProperty("webdriver.chrome.driver", "path/to/chromedriver");
              // Initialize ChromeDriver
              this.driver = new ChromeDriver();
          }
      
          // Common method to navigate to a URL
          protected void navigateToUrl(String url) {
              driver.get(url);
          }
      
          // Common method to close the browser
          protected void closeBrowser() {
              driver.quit();
          }
      }  
    
    
    Now, you can create an intermediate class, let's say `IntermediateTest`, that inherits from `BaseTest` and adds additional common functionality:
    
    
      public class IntermediateTest extends BaseTest {
      
          // Common method for some intermediate actions
          protected void performIntermediateActions() {
              // Example: perform some intermediate actions using the driver
          }
      }
    
    
    Finally, you can create a specific test class, let's say `LoginTest`, that inherits from `IntermediateTest`:
    
    
      public class LoginTest extends IntermediateTest {
      
          // Test method for login functionality
          public void testLogin() {
              // Use inherited methods and properties
              navigateToUrl("https://www.example.com/login");
      
              // Perform intermediate actions using the inherited method
              performIntermediateActions();
      
              // Perform login actions using driver
      
              // Example assertion
              // assertTrue(driver.findElement(By.id("logoutButton")).isDisplayed());
      
              // Close the browser using the inherited method
              closeBrowser();
          }
      
          public static void main(String[] args) {
              // Create an object of LoginTest and run the test
              LoginTest loginTest = new LoginTest();
              loginTest.testLogin();
          }
      }
    
    
    In this example:
    
    - The `BaseTest` class provides basic setup and utility methods.
    - The `IntermediateTest` class inherits from `BaseTest` and adds some intermediate actions.
    - The `LoginTest` class inherits from `IntermediateTest` and adds specific test methods related to login functionality.
    
    This structure allows for a clear separation of concerns and promotes code reuse. Each level of the hierarchy adds functionality, and 
    specific test classes can focus on their unique aspects while benefiting from the shared functionality provided by their parent classes.

  #### Multiple inheritance

      Java doesn't support multiple inheritance through classes, but it does support multiple inheritance through interfaces. This design 
      choice was made to avoid the complexities and ambiguities associated with multiple inheritance in the context of classes.
    
    Multiple inheritance occurs when a class inherits from more than one class. In the case of Java:
    
    1. **Diamond Problem:**
       One of the main reasons for not allowing multiple inheritance in classes is the diamond problem. The diamond problem arises when a 
       class inherits from two classes that have a common ancestor. If both parent classes have a method with the same name, it becomes 
       ambiguous for the compiler to determine which method should be called when invoked through the child class.
    
       For example:
           
           class A {
               void doSomething() {
                   System.out.println("A's implementation");
               }
           }
        
           class B extends A {
               void doSomething() {
                   System.out.println("B's implementation");
               }
           }
        
           class C extends A {
               void doSomething() {
                   System.out.println("C's implementation");
               }
           }
        
           class D extends B, C {  // This is not allowed in Java
               // ...
           }
           
    
       If class `D` were allowed to inherit from both `B` and `C`, and it tried to call `doSomething()`, it would be unclear whether it 
       should use the implementation from `B` or `C`.
    
    2. **Complexity and Maintenance:**
       Multiple inheritance can lead to complex class hierarchies, making code harder to understand, maintain, and debug. It can also 
       introduce issues related to method conflicts and resolution.
    
    3. **Interface-Based Multiple Inheritance:**
       While Java doesn't support multiple inheritance with classes, it does support multiple inheritance through interfaces. A class can 
       implement multiple interfaces, allowing it to inherit method signatures from multiple sources without the same kind of complications 
       associated with class inheritance.
    
          
           interface A {
               void doSomething();
           }
        
           interface B {
               void doAnotherThing();
           }
        
           class C implements A, B {
               public void doSomething() {
                   System.out.println("C's implementation of doSomething");
               }
        
               public void doAnotherThing() {
                   System.out.println("C's implementation of doAnotherThing");
               }
           }
         
    
       In this way, Java provides a form of multiple inheritance, but it is achieved through interfaces rather than classes, mitigating the 
       issues associated with the diamond problem.
