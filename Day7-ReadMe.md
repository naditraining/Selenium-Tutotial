# Selenium advanced continuation
## Multiple windows handling
        // Get the current window handle
        String mainWindowHandle = driver.getWindowHandle();

        // Perform actions that open a new window or tab
        // For example, clicking on a link that opens a new window
        WebElement linkElement = driver.findElement(By.linkText("Open New Window"));
        linkElement.click();

        // Switch to the new window or tab
        // Get all window handles
        Set<String> allWindowHandles = driver.getWindowHandles();
        for (String windowHandle : allWindowHandles) {
            if (!windowHandle.equals(mainWindowHandle)) {
                driver.switchTo().window(windowHandle);
                break;
            }
        }

        // Perform actions on the new window or tab
        // For example, interacting with elements

        // Switch back to the main window or tab
        driver.switchTo().window(mainWindowHandle);
## Window level actions

### Maximise
        // Maximize the window
        driver.manage().window().maximize();
### Implicit timeout
    Implicit waits in Selenium WebDriver are used to set a default waiting time for the WebDriver to wait for the elements to be found in the DOM when performing actions like findElement or findElements. If the element is not immediately available, WebDriver will wait for the specified amount of time before throwing a NoSuchElementException.
    // Set implicit wait
    driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);

## Web tables

### Dynamic rows
        // Find the table element
        WebElement table = driver.findElement(By.id("customers"));

        // Find all rows of the table
        List<WebElement> rows = table.findElements(By.tagName("tr"));

        // Iterate through each row
        for (WebElement row : rows) {
            // Find all columns of the row
            List<WebElement> columns = row.findElements(By.tagName("td"));

            // Iterate through each column
            for (WebElement column : columns) {
                // Print the text of each cell
                System.out.print(column.getText() + "\t");
            }
            // Print a new line after each row
            System.out.println();
        }
## Keys in sendKeys method

    chrome.findElement(By.id("sdfs")).sendKeys("hi",Keys.TAB);

## Explicit timeout 

        Explicit timeouts in Selenium WebDriver are used to set the maximum time WebDriver should wait for a certain condition to be met before throwing an exception.
        // Initialize WebDriverWait with a timeout of 10 seconds
        WebDriverWait wait = new WebDriverWait(driver, 10);

        // Wait for the element to be clickable
        WebElement element = wait.until(ExpectedConditions.elementToBeClickable(By.id("element_id")));

        // Perform actions on the element
        element.click();
