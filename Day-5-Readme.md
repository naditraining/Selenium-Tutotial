## Evolution of Selenium:

  Selenium Core (2004)
  Selenium RC (Remote Control) (2006)
  Selenium WebDriver (2009): 
  Selenium Grid (2011): 
  Selenium 2 (2011):
  Selenium 3 (2016):
  Selenium 4 (2020):

## Components of selenium 

<img width="772" alt="image" src="https://github.com/naditraining/Selenium-Tutotial/assets/157560787/a969948c-0027-47cd-badf-6384f82d56dd">

Note: Selenium RC is deprecated from Selenium 2, as web driver is better than RC.

## Supported Browsers:
  
  Chrome
  Edge
  Safari
  Firefox
  Internet explorer

## Selenium 3 architecture

<img width="651" alt="image" src="https://github.com/naditraining/Selenium-Tutotial/assets/157560787/7bcd657d-2b96-4368-bdca-5127b306e581">


## Selenium 4 architecture

<img width="660" alt="image" src="https://github.com/naditraining/Selenium-Tutotial/assets/157560787/c0a33426-de08-4cb6-81c3-a1ba0e56428d">

## Whats new in Selenium 4

  1. Enhanced Selenium Grid
  2. Upgraded Selenium IDE
  3. Relative Locators in Selenium 4
  4. Improved Documentation
  5. Support for Chrome Debugging Protocol
  6. Better Window/Tab Management in Selenium 4
  7. Deprecation of Desired Capabilities
  8. Modifications in the Actions Class

  For more detailed informaiton, refer the source article: https://www.browserstack.com/guide/selenium-4-features

## No need to mention Driver path hereafter (starting selenium 4.6)

  Selenium now has its own driver manager to download the required version of driver in the background.
  
  more information can be found here
  
  https://www.selenium.dev/documentation/selenium_manager/

## Sample HTML page and DOM

<img width="1182" alt="image" src="https://github.com/naditraining/Selenium-Tutotial/assets/157560787/ad4f8d2b-f004-40fe-8f1f-69615af70920">

### Basic html tags

    In HTML (Hypertext Markup Language), tags and attributes play a crucial role in structuring and defining the content of a document. Here's a brief explanation of basic tags and attributes commonly used in an HTML document:
    
    1. **HTML Tag (`<html>`):**
       - The `<html>` tag is the root element of an HTML document.
       - It contains the entire HTML content, including the document structure, head, and body.
    
    2. **Head Tag (`<head>`):**
       - The `<head>` tag is used to define the head section of an HTML document.
       - It contains meta-information about the HTML document, such as the title, character set, links to external stylesheets, and more.
    
    3. **Title Tag (`<title>`):**
       - The `<title>` tag is used within the `<head>` section to define the title of the HTML document.
       - The title appears in the browser's title bar or tab.
    
    4. **Body Tag (`<body>`):**
       - The `<body>` tag contains the main content of the HTML document, including text, images, links, forms, and other elements.
    
    5. **Heading Tags (`<h1>` to `<h6>`):**
       - Heading tags are used to define headings and subheadings in the document.
       - `<h1>` is the highest level (main heading), and `<h6>` is the lowest level (sub-sub-sub-subheading).
    
    6. **Paragraph Tag (`<p>`):**
       - The `<p>` tag defines a paragraph in the document.
       - Text within `<p>` tags is typically separated from other content, and browsers add spacing before and after the paragraph.
    
    7. **Anchor Tag (`<a>`):**
       - The `<a>` tag creates hyperlinks and is used to link to other web pages or resources.
       - The `href` attribute specifies the URL of the linked resource.
    
    8. **Image Tag (`<img>`):**
       - The `<img>` tag is used to embed images in the document.
       - The `src` attribute specifies the source URL of the image.
    
    9. **List Tags (`<ul>`, `<ol>`, `<li>`):**
       - `<ul>` creates an unordered list (bullet points).
       - `<ol>` creates an ordered list (numbered).
       - `<li>` defines list items within `<ul>` or `<ol>`.
    
    10. **Division Tag (`<div>`):**
        - The `<div>` tag is a container element used to group and structure other HTML elements.
        - It is often used with CSS for styling and layout purposes.
    
    11. **Attribute (e.g., `class`, `id`, `style`):**
        - Attributes provide additional information about HTML elements.
        - `class` is used to assign one or more class names for styling.
        - `id` provides a unique identifier for an element.
        - `style` allows inline CSS styling for an individual element.
    
    These are just a few basic tags and attributes in HTML. HTML offers a wide range of tags and attributes to structure and style content, and it is essential to understand their usage for creating well-formed and semantically meaningful web documents.

## Basic automation principle

  - Launch browser (create driver object) 
  
  - Locate the element (using the driver object and use find element methods (returns the webelment object)  
  
  - Do the action (use the web element object and call the necessary action methods) 
  
  - Eaplain the browser (window) and element level operations.

## Driver level functions

  In Selenium, driver level functions refer to the methods and capabilities provided by the WebDriver interface to interact with and control the browser. The       WebDriver interface serves as the foundation for various browser-specific implementations like ChromeDriver, FirefoxDriver, etc. Here are some common driver-     level functions in Selenium:
  
  1. **Creating a WebDriver instance:**
     - Instantiate a specific WebDriver class to launch and control a particular browser.
     ```java
     WebDriver driver = new ChromeDriver(); // For Chrome browser
     ```
  
  2. **Navigating to a URL:**
     - Use the `get()` method to navigate to a specific URL.
     ```java
     driver.get("https://example.com");
     ```
  
  3. **Navigating forward and backward:**
     - Use `navigate().forward()` and `navigate().back()` methods to navigate forward and backward in the browser history.
     ```java
     driver.navigate().forward();
     driver.navigate().back();
     ```
  
  4. **Refreshing the page:**
     - Use `navigate().refresh()` to refresh the current page.
     ```java
     driver.navigate().refresh();
     ```
  
  5. **Managing browser windows:**
     - Functions like `getWindowHandle()`, `getWindowHandles()`, `switchTo().window()`, and `close()` help in managing browser windows and tabs.
     ```java
     String currentWindow = driver.getWindowHandle();
     Set<String> allWindows = driver.getWindowHandles();
     driver.switchTo().window(currentWindow);
     driver.close();
     ```
  
  6. **Finding elements:**
     - Use various `findElement()` and `findElements()` methods to locate and interact with HTML elements on the page.
     ```java
     WebElement element = driver.findElement(By.id("exampleId"));
     List<WebElement> elements = driver.findElements(By.tagName("a"));
     ```
  
  7. **Interacting with elements:**
     - WebDriver provides methods to interact with elements, such as `click()`, `sendKeys()`, `getText()`, `getAttribute()`, etc.
     ```java
     element.click();
     element.sendKeys("input text");
     String text = element.getText();
     String attributeValue = element.getAttribute("attributeName");
     ```
  
  8. **Handling alerts:**
     - Methods like `switchTo().alert().accept()`, `switchTo().alert().dismiss()`, and `switchTo().alert().getText()` are used to handle JavaScript alerts.
     ```java
     driver.switchTo().alert().accept();
     ```
  
  9. **Executing JavaScript:**
     - Use `executeScript()` to execute JavaScript code in the context of the current page.
     ```java
     JavascriptExecutor jsExecutor = (JavascriptExecutor) driver;
     jsExecutor.executeScript("document.getElementById('elementId').style.border='2px solid red'");
     ```
  
  10. **Managing timeouts:**
      - Use `manage().timeouts()` to set implicit and page load timeouts.
      ```java
      driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
      ```

  10. **Managing window:**
      - Use `manage().window()` to minimize and maximise the window.

          WebDriver driver = new ChromeDriver();
          driver.get("https://example.com");
          
          // Maximize the browser window
          driver.manage().window().maximize();

         // Minimize the browser window
         driver.manage().window().minimize();

  These are just a few examples of driver-level functions provided by Selenium. Depending on your testing requirements, you may need to use additional methods and capabilities provided by the WebDriver interface.

## How we locate the elements in page - Locators in selenium 

    Locator  	      Description
    
    class name	        - Locates elements whose class name contains the search value (compound class names are not permitted)
    css selector	      - Locates elements matching a CSS selector
    id	                - Locates elements whose ID attribute matches the search value
    name	              - Locates elements whose NAME attribute matches the search value
    link text	          - Locates anchor elements whose visible text matches the search value
    partial link text	  - Locates anchor elements whose visible text contains the search value. If multiple elements are matching, only the                           first one will be selected.
    tag name	          - Locates elements whose tag name matches the search value
    xpath	              - Locates elements matching an XPath expression


    <img width="756" alt="image" src="https://github.com/naditraining/Selenium-Tutotial/assets/157560787/e387b606-9911-431c-8b3f-6f5fcb584268">
### Xpath
    
    Syntax - Xpath =//tagname[@Attribute=’value’]

### CSS selector 
    
    https://www.browserstack.com/guide/css-selectors-in-selenium 
    
    practice CSS selector here
    https://www.w3schools.com/cssref/trysel.php

### Xpath vs CSS

    ![image](https://github.com/naditraining/Selenium-Tutotial/assets/157560787/ebb086ff-4807-4ca1-bbed-571551f2598a)

    An axis represents a relationship to the context (current) node, and is used to locate nodes relative to that node on the tree.
    
## Relative locators from Selenium 4

    Selenium 4 introduces Relative Locators (previously called Friendly Locators). These locators are helpful when it is not easy to       
    construct a locator for the desired element, but easy to describe spatially where the element is in relation to an element that does 
    have an easily constructed locator.

    options are - above, below, toLeftOf, toRightOf.

## references
    https://testsigma.com/blog/xpath-vs-css-selector/#Advantages_of_CSS_Selectors_over_XPath
