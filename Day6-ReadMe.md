#   Interacting with basic elements
## Text Box
        WebDriver driver = new ChromeDriver();

        // Implicit wait
        driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);

        // Navigate to the webpage with the text box
        driver.get("https://example.com");

        // Find the text box by its ID (replace "textbox_id" with the actual ID of the text box)
        WebElement textBox = driver.findElement(By.id("textbox_id"));

        // Enter text into the text box
        textBox.sendKeys("Hello, World!");
## Button
        WebDriver driver = new ChromeDriver();

        // Implicit wait
        driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);

        // Navigate to the webpage with the button
        driver.get("https://example.com");

        // Find the button by its ID, XPath, CSS Selector, or other locator strategies
        WebElement button = driver.findElement(By.id("button_id"));

        // Click the button
        button.click();
## Check box
        // Find the checkbox by its ID, XPath, CSS Selector, or other locator strategies
        WebElement checkbox = driver.findElement(By.id("checkbox_id"));

        // Check if the checkbox is selected
        boolean isChecked = checkbox.isSelected();
        System.out.println("Is checkbox selected? " + isChecked);

        // Click the checkbox to select it (if it's not already selected)
        if (!isChecked) {
            checkbox.click();
        }
## Radio button
        WebElement radioButton = driver.findElement(By.id("radio_button_id"));

        // Check if the radio button is selected
        boolean isSelected = radioButton.isSelected();
        System.out.println("Is radio button selected? " + isSelected);

        // Click the radio button to select it (if it's not already selected)
        if (!isSelected) {
            radioButton.click();
        }
## Button
        // Find the button by its ID, XPath, CSS Selector, or other locator strategies
        WebElement button = driver.findElement(By.id("button_id"));

        // Click the button
        button.click();
## Drop down
        // Find the dropdown by its ID, XPath, CSS Selector, or other locator strategies
        WebElement dropdown = driver.findElement(By.id("dropdown_id"));

        // Create a Select object
        Select selectDropdown = new Select(dropdown);

        // Select an option by visible text
        selectDropdown.selectByVisibleText("Option 1");

        // Alternatively, you can select an option by value or index
        // selectDropdown.selectByValue("value_of_option");
        // selectDropdown.selectByIndex(index_of_option);

## Screenshot
        // Convert WebDriver object to TakesScreenshot
        TakesScreenshot screenshot = (TakesScreenshot) driver;

        // Capture the screenshot as a File
        File srcFile = screenshot.getScreenshotAs(OutputType.FILE);

        // Specify the location to save the screenshot
        File destFile = new File(fileName);

        // Copy the screenshot to the desired location
        try {
            Files.copy(srcFile.toPath(), destFile.toPath());
            System.out.println("Screenshot captured: " + destFile.getAbsolutePath());
        } catch (IOException e) {
            e.printStackTrace();
        }
## Alerts
        // Switch to the alert
        Alert alert = driver.switchTo().alert();

        // Get the text from the alert
        String alertText = alert.getText();
        System.out.println("Alert text: " + alertText);

        // Enter text into the alert (if it's a prompt)
        // alert.sendKeys("Your response");

        // Accept the alert (click OK)
        alert.accept();

        // Dismiss the alert (click Cancel)
        // alert.dismiss();

        // Switch back to the main window (if needed)
        // driver.switchTo().defaultContent();
## Frames
            // Switch to the frame by index (0-based index)
        driver.switchTo().frame(0);

        // Switch to the frame by name or ID
        // driver.switchTo().frame("frame_name_or_id");

        // Switch to the frame by WebElement
        // WebElement frameElement = driver.findElement(By.id("frame_id"));
        // driver.switchTo().frame(frameElement);

        // Now you are inside the frame, perform actions within the frame
        // For example, find elements and interact with them
        WebElement elementInFrame = driver.findElement(By.id("element_id_inside_frame"));
        elementInFrame.click();

        // Switch back to the main content (if needed)
        driver.switchTo().defaultContent();

## Close vs quit
    close(): This method closes the currently focused browser window or tab. 
    quit(): This method closes all the browser windows or tabs opened by the WebDriver.
## Advance elements
### Mouse actions 
#### Mouse hover
        // Find the element to hover over
        WebElement elementToHover = driver.findElement(By.id("element_id"));

        // Create an instance of Actions class
        Actions actions = new Actions(driver);

        // Perform mouse hover action on the element
        actions.moveToElement(elementToHover).perform();

        // Perform additional actions like clicking a sub-element after hover
        WebElement subElement = driver.findElement(By.id("sub_element_id"));
        subElement.click();
#### Scrolling
        // Create an instance of JavascriptExecutor
        JavascriptExecutor js = (JavascriptExecutor) driver;

        // Scroll down by pixel
        js.executeScript("window.scrollBy(0,500)");

        // Alternatively, you can scroll to a specific element
        // WebElement element = driver.findElement(By.id("element_id"));
        // js.executeScript("arguments[0].scrollIntoView();", element);

        // Scroll to the bottom of the page
        // js.executeScript("window.scrollTo(0, document.body.scrollHeight)");
#### Right click
        // Create an instance of Actions class
        Actions actions = new Actions(driver);

        // Perform right-click action on the element
        actions.contextClick(elementToRightClick).perform();
#### Double click
        // Find the element to double-click
        WebElement elementToDoubleClick = driver.findElement(By.id("element_id"));

        // Create an instance of Actions class
        Actions actions = new Actions(driver);

        // Perform double-click action on the element
        actions.doubleClick(elementToDoubleClick).perform();

#### Drag and drop
        // Find the source element to drag
        WebElement sourceElement = driver.findElement(By.id("todrag"));

        // Find the target element to drop onto
        WebElement targetElement = driver.findElement(By.id("mydropzone"));

        // Create an instance of Actions class
        Actions actions = new Actions(driver);

        // Perform drag-and-drop action
        actions.dragAndDrop(sourceElement, targetElement).perform();
### Keyboard actions
        // Create an instance of Actions class
        Actions actions = new Actions(driver);

        // Perform keyboard actions
        actions.click(searchBox) // Click on the search box to focus it
                .sendKeys("Selenium WebDriver") // Enter text
                .sendKeys(Keys.ENTER) // Press Enter key
                .perform(); // Perform the actions
 

