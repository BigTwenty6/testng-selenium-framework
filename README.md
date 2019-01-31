git # testng-selenium-framework

Frame Work scratch

how to create testng. runners:

Create new runner:
file --> new file , for regression ---> file name = regression_runner.xml

How to rune test from command line / Terminal

     all smoke test are autometed. They are schedule and triggered by a different software: Jenkins , Bamboo , Travis

     CI tools run the test using maven. We can use maven commands to run our tests and generate reports.

     in our framework we comannd mv test to run our tests.


maven - surefire-plugin. --> used during the test lifecycle of maven, can be used to idicate whuch file we run , if there are reports , it will also generate reports. -->

<build>
        <plugins>

            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-surefire-plugin</artifactId>
                <version>2.21.0</version>
                <configuration>
                    <suiteXmlFiles>
                        <suiteXmlFile>testng_runner.xml</suiteXmlFile>
                    </suiteXmlFiles>
                </configuration>
            </plugin>

        </plugins>
    </build>

 1.We tell maven to run tests: mvn test
 1.maven asks  pom file  which tests to run
 3. poom file tells :
   <suiteXmlFile>testng_runner.xml</suiteXmlFile>
                    </suiteXmlFiles>

 4.testng_runner.xml will be executed


 Talk about FrameWork :

 Data driven FrameWork (DD )
    A framework where tests are executed based on set of data , framework is designed to read data from outside sources like excel and run tests based on the data. In data driven framework we can execute teh same tests multiple times against different sets of data

 Page Object Model FrameWork
   uses the page object design pattern according to which we create a separate java class for each page of the application

 Behavior Driven FrameWork  (BDD)
   We will talk about it later


 KeyWord Driven FrameWork
    In KDF we use keywords int outside source (excel, csv) to run our tests. Framework is designed to read the data and steps from excel and execute actions based on it.
    Once KDF is set up even no technical tester can write and excecute automated tests.

 Hybrid FrameWork
   Is a framework uses at least two of the types given above


   TALK ABOUT FRAMEWORK

    TOOLS :

      Java : My FrameWork is written using Java language

      Maven: My FrameWork created as maven projecect , maven is used to manage dependecies
      and also we use to run our tests as mvn goals from terminal

      Selenium WebDriver: A libary/tool/api which is used to automate the browser
      it interacts with the browser


      TestNG: Used to run tests as groups using .xml files, do soft and hard assertions
      create test methods , (We chose what to run)

      Extent Reporting FrameWork: My FrameWork generates detailed HTML report which is easy to read and understand to non technical people team members. My reports have details test steps and screenShots any failueres that may occur. It can also do metrics on what percentage is passing , failling, skipped etc

      IDE: I use intelliJ in my current FrameWork , but I'm also comfortable with Eclipse which I used previously.

    Design:
      Page Object Model: My FrameWork uses Page Object Model according to which I created a separate classes for the pages of my Application.
      Page Factory Design: A Design which makes it easy to access the page object class.

      Singleton Driver: My FrameWork uses a singleton pattern to share the WebDriver instance between different classes

      Test Base : My FrameWork has a TestBase class which my test extend.
      TestBase class has the common steps for all my test.

      Configuration File : Used to store the important test data

      Utilities : have reusable utilities which can be used accros differen classes of my FrameWork

    Benefit:   Easy to maintain : My FrameWork uses Page Object Model which makes it easy to maintain.  for example  if I have to update any Locator , I only need to one code change .
     I try to make my test independent from each other. This mean if I update one test it will not effect other, also if one fails other will not be affected.

    Easy to extend: It is easy to add new test cases to my FrameWork.

    Easy to reuse : I have Page Object model, utilities which I can reuse for any test.

    Multi browser testing: My FrameWork can run the same tests against different browsers with minimal code change

    Types of tests: My FrameWork can test the UI, DataBase and API of the application

    Packaging: I have create different package for different typse of classes and logic. Each page package only contains classes with same functionlaty.

    Naming conventions: In my team we pay a lot of attention to coding standars, espacially naming conventions . Classes , methods veriable are named on based on what they do and follow a standard
       Page object class:
           homePage, LoginPage

      Variable : loginButton , SignOutButonn


      Methods: login(); this method only used to login, not for other functionality.

