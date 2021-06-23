# JByfield-NHSBSA
To run this test, please follow these instructions: 

1). You will need MS Visual Studio installed, the basic community version will be ok. 

2). Unzip the files. 

3). Open the .sln file with MS Visual Studio. You will need to restore the Nuget packages, there will be a yellow warning box towards the top of the screen for this. 

4). Open the Test.Runsettings file and change the value on the BrowserType tag to fit the browser you are wanting to run it on 
    The full list is as follows: 
        IE,
        Remote,
        FireFox,
        Chrome,
        ChromeHeadless

5). If needed manually point Visual Studio to the location of the Test.RunSettings file. This will also solve 99% of all 'object not set to an instance of an object' errors as well. 

6). Run the test from the Test Explorer. 

The whole project uses C# Selenium, with the Page Object Models and Nunit. 
The webdriver, along with the waits and alerts handlers are initiallised in the Base Class
The selection of the relevant webrdiver type plus setup and tear-down is handled in the Hooks Class

Each webpage has its own class, containing the relevant page objects and associated methods
These classes are all turned into static classes using the page class. This helps reduce the amount of code written for each test class. 
When moving to a new webpage there is always a wait followed by an assert that checks we are on the right page. 
The relevant actions are then carried out before moving to the next page. 

Each test has its own class, the code in each of these is kept to a minimum with the methods written out in the classes for each individual page. 
