#  Page object model

##  why POM 
    Modularity and Reusability
    Code Maintainability
    Improved Readability

##  How to implement POM 
    1. Create Base Class and have common code like browser object creation and test data read.
    2. Create java class for each page in the application and extend Base Class
    3. Implement a method for each action in the given page 
    4. Call the page classes from step definition file.

Note: you can choose to keep the driver object as static, so it can be directly accessed by any class like step definition or page class.

## Issue when the tests run parallel
## Cucumber hooks
## Extent report adapter 
## GitHub
