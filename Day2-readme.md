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

### 
