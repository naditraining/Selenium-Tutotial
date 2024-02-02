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

### Polymorphism

#### method overloading 

    Method overloading in Java allows a class to have multiple methods with the same name but with different parameter lists. The key point     is that the methods must have a different number or type of parameters. This provides flexibility and readability in the code by            allowing you to use the same method name for operations that conceptually do the same thing but may vary based on the input

    import org.openqa.selenium.WebDriver;
    import org.openqa.selenium.chrome.ChromeDriver;
    import org.openqa.selenium.firefox.FirefoxDriver;
    import org.openqa.selenium.edge.EdgeDriver;
    
    public class BrowserLauncher {
    
        // Method to launch Chrome browser
        public static WebDriver launchChromeBrowser() {
            System.setProperty("webdriver.chrome.driver", "path/to/chromedriver");
            return new ChromeDriver();
        }
    
        // Method to launch Firefox browser
        public static WebDriver launchFirefoxBrowser() {
            System.setProperty("webdriver.gecko.driver", "path/to/geckodriver");
            return new FirefoxDriver();
        }
    
        // Method to launch Edge browser
        public static WebDriver launchEdgeBrowser() {
            System.setProperty("webdriver.edge.driver", "path/to/msedgedriver");
            return new EdgeDriver();
        }
    
        // Overloaded method to launch Chrome browser with custom options
        public static WebDriver launchChromeBrowser(String chromeOptions) {
            System.setProperty("webdriver.chrome.driver", "path/to/chromedriver");
            // Additional code to configure Chrome options based on the input
            // For simplicity, we'll just print the options in this example
            System.out.println("Chrome Options: " + chromeOptions);
            return new ChromeDriver();
        }
    
        public static void main(String[] args) {
            // Example usage of the overloaded methods
            WebDriver chromeDriver = launchChromeBrowser();
            WebDriver firefoxDriver = launchFirefoxBrowser();
            WebDriver edgeDriver = launchEdgeBrowser();
            WebDriver customChromeDriver = launchChromeBrowser("--headless");
    
            // Perform actions with the launched browsers (not shown in this example)
            
            // Close the browsers when done
            chromeDriver.quit();
            firefoxDriver.quit();
            edgeDriver.quit();
            customChromeDriver.quit();
        }
    }

    These methods are overloaded because they have the same method name (launchChromeBrowser) but different parameter lists (in terms of the number and types of parameters).

#### Method overriding

    Method overriding in Java is a feature that allows a subclass to provide a specific implementation of a method that is already defined in its superclass. The overriding method should have the same method signature (name, return type, and parameters) as the method in the superclass. Method overriding is a form of runtime polymorphism, where the actual method that gets executed is determined at runtime based on the object's type.

        import org.openqa.selenium.WebDriver;
    import org.openqa.selenium.chrome.ChromeDriver;
    import org.openqa.selenium.firefox.FirefoxDriver;
    
    class BrowserLauncher {
        // Method to launch a generic browser
        void launchBrowser() {
            System.out.println("Launching a generic browser");
        }
    }
    
    class ChromeBrowserLauncher extends BrowserLauncher {
        // Override the launchBrowser method for Chrome
        @Override
        void launchBrowser() {
            System.setProperty("webdriver.chrome.driver", "path/to/chromedriver");
            WebDriver driver = new ChromeDriver();
            System.out.println("Launching Chrome browser");
            // Additional configuration or actions specific to Chrome
        }
    }
    
    class FirefoxBrowserLauncher extends BrowserLauncher {
        // Override the launchBrowser method for Firefox
        @Override
        void launchBrowser() {
            System.setProperty("webdriver.gecko.driver", "path/to/geckodriver");
            WebDriver driver = new FirefoxDriver();
            System.out.println("Launching Firefox browser");
            // Additional configuration or actions specific to Firefox
        }
    }
    
    public class BrowserLauncherTest {
        public static void main(String[] args) {
            BrowserLauncher chromeLauncher = new ChromeBrowserLauncher();
            BrowserLauncher firefoxLauncher = new FirefoxBrowserLauncher();
    
            chromeLauncher.launchBrowser();  // Calls the overridden method in ChromeBrowserLauncher
            firefoxLauncher.launchBrowser(); // Calls the overridden method in FirefoxBrowserLauncher
        }
    }


Explanation:

BrowserLauncher is the base class with a method launchBrowser. This method prints a generic message indicating the launch of a generic browser.

ChromeBrowserLauncher and FirefoxBrowserLauncher are subclasses of BrowserLauncher. They override the launchBrowser method to provide browser-specific implementations for Chrome and Firefox, respectively.

### Arrays in Java

  In Java, an array is a data structure that allows you to store multiple values of the same type under a single variable name. It provides a way to access elements using an index or position within the array. The index starts from 0, so the first element is at index 0, the second element at index 1, and so on.

  #### Declaration and Initialization:

    // Declaration and initialization of an array of integers
    int[] numbers = {1, 2, 3, 4, 5};
    
    // Declaration and initialization of an array of strings
    String[] names = {"Alice", "Bob", "Charlie", "David"};

  #### Accessing Array Elements:

    int firstNumber = numbers[0];  // Access the first element (index 0)
    String secondName = names[1];  // Access the second element (index 1)

  #### Array length

    int lengthOfNumbers = numbers.length;  // Returns the length of the numbers array

  #### Example

      public class ArrayExample {
        public static void main(String[] args) {
            // Declaration and initialization of an array of integers
            int[] numbers = {10, 20, 30, 40, 50};
    
            // Accessing and printing array elements
            System.out.println("First number: " + numbers[0]);
            System.out.println("Second number: " + numbers[1]);
            System.out.println("Third number: " + numbers[2]);
    
            // Modifying an array element
            numbers[1] = 25;
            System.out.println("Updated second number: " + numbers[1]);
    
            // Iterating through the array using a for loop
            System.out.println("Array elements:");
            for (int i = 0; i < numbers.length; i++) {
                System.out.println("Element at index " + i + ": " + numbers[i]);
            }
        }
    }



