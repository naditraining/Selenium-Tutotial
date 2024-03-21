### browser launch in selenium 3 using web driver manger 
        WebDriverManager.chromedriver().setup();
        //System.setProperty("webdriver.chrome.driver","/Users/nadimuthujayapal/TrainingNotes/grid/chromedriver.exe");
        ChromeDriver chrome = new ChromeDriver();
        chrome.get("https://www.irctc.co.in/nget/profile/user-registration");
### how to interact
        //find the element
        WebElement username =  chrome.findElementById("userName");
        //apply the appropriate action
        username.sendKeys("nadiyhyh");
## by xpath

        WebElement password = chrome.findElementByXPath("//input[@placeholder=\"User Name\"]");
        password.click();

## interact with drop down
        //drop down
        WebElement countryDropdown = chrome.findElementByXPath("//input[@placeholder=\"User Name\"]");

        Select select = new Select(countryDropdown);
        select.selectByIndex(4);
        select.selectByVisibleText("India");
        select.selectByValue("valuename");
        
## how to interact link

        chrome.findElementByLinkText();
        chrome.findElementByPartialLinkText();

## CSS ???
## file upload  ???

