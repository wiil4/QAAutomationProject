# QA Automation Project with C# and Selenium
This a project for testing some functionalities on [yopmail](https://yopmail.com/es/) and [todoist](https://todoist.com/es)

## Specifications
- Depending on the test page, is necessary to comment or uncomment the TestMethod attribute

## YopMailTest
- It has it's own files inside folder page/YopMail and test/YopMail
- For testing is necessary to make sure the **TestMethod** is uncommented in file **test/YopMail/SendMailTest.cs** and **TestMethod** of todoist is commented in file **test/Todoist/CRUDTest.cs**
- It is also necessary to uncomment the driver navigator which is located in *BaseTest.cs* as explained below:

```csharp
[TestInitialize]
    public void OpenBrowser()
    {
        Session.Instance().GetBrowser().Navigate().GoToUrl("https://yopmail.com/");
        //Session.Instance().GetBrowser().Navigate().GoToUrl("https://todoist.com/");
    }
```

## TotoistTest
- It has it's own files inside folder page/Todoist and test/Todoist
- For testing is necessary to make sure **todoist** TestMethod is uncommented as **yopmail** TestMethod is uncommented
- It is also necessary to uncomment the driver navigator which is located in **test/Todoist/CRUDTest.cs** as explained below:

```csharp
[TestInitialize]
    public void OpenBrowser()
    {
        //Session.Instance().GetBrowser().Navigate().GoToUrl("https://yopmail.com/");
        Session.Instance().GetBrowser().Navigate().GoToUrl("https://todoist.com/");
    }
```

- In addition, tester should provide a correct **User email** and **Password** (that has been Signed Up in Todoist) in the file (**test/Todoist/CRUDTest.cs**) explained below:

```csharp
public class CRUDTest : BaseTest
    {
        MainPage mainPage = new MainPage();
        LogInPage logInPage = new LogInPage();
        ProjectsSection projectsSection = new ProjectsSection();

        private readonly string email = "";
        private readonly string password = "";
    ...
```