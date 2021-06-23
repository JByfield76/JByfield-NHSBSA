# JByfield-NHSBSA
To run this test, please follow these instructions: 

1). Download into MS Visual Studio. 

2). Open the Test.Runsettings file and change the value on the BrowserType tag to fit the browser you are wanting to run it on 
    The full list is as follows: 
        IE,
        Remote,
        FireFox,
        Chrome,
        ChromeHeadless

3). If needed reload/refresh the Nuget packages and manually point Visual Studio to the location of the Test.RunSettings file. 

4). Run the test from the Test Explorer. 

The whole project uses C# Selenium, with the Page Object Models and Nunit. 
The webdriver, along with the waits and alerts handlers are initiallised in the Base Class
The selection of the relevant webrdiver type plus setup and tear-down is handled in the Hooks Class

Each webpage has its own class, containing the relevant page objects and associated methods
These classes are all turned into static classes using the page class. This helps reduce the amount of code written for each test class. 
When moving to a new webpage there is always a wait followed by an assert that checks we are on the right page. 
The relevant actions are then carried out before moving to the next page. 

Each test has its own class, the code in each of these is kept to a minimum with the methods written out in the classes for each individual page. 
