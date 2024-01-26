# Selenium-Tutotial
## Introduction to automation testing
### Why Selenium 
### Sample Selenium program

 
      package org.example;
      
      import org.openqa.selenium.By;
      import org.openqa.selenium.WebDriver;
      import org.openqa.selenium.WebElement;
      import org.openqa.selenium.chrome.ChromeDriver;
      
      import java.time.Duration;
      
      public class SampleSeleniumScript {
          public static void main(String[] args) {
              WebDriver driver = new ChromeDriver();
      
              driver.get("https://www.selenium.dev/selenium/web/web-form.html");
      
              driver.getTitle();
      
              driver.manage().timeouts().implicitlyWait(Duration.ofMillis(500));
      
              WebElement textBox = driver.findElement(By.name("my-text"));
              WebElement submitButton = driver.findElement(By.cssSelector("button"));
      
              textBox.sendKeys("Selenium");
              submitButton.click();
      
              WebElement message = driver.findElement(By.id("message"));
              message.getText();
      
              driver.quit();
          }
      }

### Pre requisites for selenium
    1: Language - Install Java Development Kit (JDK)
    2: IDE (Editor) - Install IntelliJ IDEA

## JAVA, Installation, Setting environment variable
### Java versions
1. **Java 1.0 (January 23, 1996):** The initial version of Java introduced by Sun Microsystems.

2. **Java 1.1 (February 19, 1997):** Added significant new features, including the AWT event model, JDBC, and JavaBeans.

3. **Java 1.2 (December 8, 1998):** Introduced major enhancements, including the Swing GUI toolkit, Collections framework, and the Java Naming and Directory Interface (JNDI).

4. **Java 1.3 (May 8, 2000):** Included the HotSpot JVM, introduced the Java Naming and Directory Interface (JNDI), and improved performance.

5. **Java 1.4 (February 6, 2002):** Featured the addition of the assert keyword, regular expressions, and the Logging API.

6. **Java 5 (September 30, 2004):** Introduced major language enhancements, including generics, metadata annotations, enumerated types, and the enhanced for loop.

7. **Java 6 (December 11, 2006):** Included improvements such as scripting support (via the inclusion of the Java Compiler API), JDBC 4.0, and enhancements to the Java Virtual Machine (JVM).

8. **Java 7 (July 28, 2011):** Introduced features such as the try-with-resources statement, the diamond operator for generic instances, and the Fork/Join framework for parallel programming.

9. **Java 8 (March 18, 2014):** Featured major enhancements, including lambdas, the Stream API, the java.time package for date and time, and the Nashorn JavaScript engine.

10. **Java 9 (September 21, 2017):** Introduced the module system (Project Jigsaw), the JShell REPL (Read-Eval-Print Loop), and various improvements to the Java platform.

11. **Java 10 (March 20, 2018):** Included local-variable type inference (var) and other minor enhancements.

12. **Java 11 (September 25, 2018):** A long-term support (LTS) release, introduced the HTTP Client API, local-variable syntax for lambda parameters, and other improvements.

13. **Java 12 (March 19, 2019):** Featured enhancements like switch expressions and improvements to the garbage collector.

14. **Java 13 (September 17, 2019):** Included text blocks, enhancements to the Z Garbage Collector, and more.

15. **Java 14 (March 17, 2020):** Introduced records, pattern matching for instanceof, and the foreign function and memory API.

16. **Java 15 (September 15, 2020):** Included sealed classes, pattern matching for switch, and other enhancements.

17. **Java 16 (March 16, 2021):** Featured pattern matching for the instanceof operator, Unix domain socket channel, and improvements to the garbage collector.

18. **Java 17 (September 14, 2021):** A long-term support (LTS) release, included features like Sealed Classes, Foreign Function & Memory API updates, and more.

### JAVA installation

Check if Java is Installed using below command

java -version

if not installed, 

Install JDK using below steps

https://www.oracle.com/java/technologies/javase/jdk11-archive-downloads.html

things to consider before downloading
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


