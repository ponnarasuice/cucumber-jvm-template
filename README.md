## Before run the project 
- Make sure you have chrome driver before running. 
-  set the path in the package name 'step_definitions'.Hooks.class -> openbrowser() method and modify the chromedriver.exe path
- existing tests failed due to invalid user/pass in site http://automationpractice.com
### to run
- go to folder > mvn clean package or install
-  this will run all the test cases and execute in the chrome driver browser

### execution steps
- starts with features -> different files. each feature files have different steps.
```
shoppingcart.feature
  Scenario: Sign in and sign out
    When I open automationpractice website
```
- steps are defined in the java class
```
shoppingcart.java
    @When("^I open automationpractice website$")
    public void i_open_automationpractice_website() throws Throwable {
        // Write code here that turns the phrase above into concrete actions
    	driver.get("http://automationpractice.com");
    }
        @When("^I sign in$")
    public void i_sign_in() throws Throwable {
        // Write code here that turns the phrase above into concrete actions
    	PageFactory.initElements(driver, AutomationHomePage.class);
		PageFactory.initElements(driver, LoginPage.class);// after signin login page executed
		SignInAction.Execute(driver,datamap.get(0));
    }
    
```

cucumber-jvm-template
=====================

This is a template project that you can use to start with cucumber-jvm and selenium java tests. Read about it on [seleniumframework.com](http://www.seleniumframework.com/cucumber-jvm-3/cucumber-jvm-and-selenium/)

# Full Tutorials

[Basic Tutorial](http://www.seleniumframework.com/cucumber-jvm-3/cucumber-jvm-and-selenium/)  
[Intermediate Tutorial](http://www.seleniumframework.com/cucumber-jvm-3/parameterize-browser/)  
[Advanced Tutorial/Frameworks](http://www.seleniumframework.com/cucumber-jvm-3/what-are-frameworks/)
