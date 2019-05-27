# Robotframework
Web testing with Robot Framework and SeleniumLibrary



`installation instructions`__.

In practice it is easiest to install Robot Framework and
SeleniumLibrary along with its dependencies using `pip`_ package
manager. Once you have pip installed, all you need to do is running
these commands::

    pip install robotframework
    pip install robotframework-seleniumlibrary

Note:
1. clone git repository (git clone https://github.com/amit-003/Robotframework.git)
2. cd Robotframework


 Note: Before running test cases run command line::

    python app/server.py



Running tests
-------------

The `test cases`_ are located in the ``login_tests`` directory. They can be
executed using the ``robot`` command::

    robot login_tests

.. note:: If you are using Robot Framework 2.9 or earlier, you need to
          use the ``pybot`` command instead.

You can also run an individual test case file and use various command line
options supported by Robot Framework::

    robot login_tests/valid_login.robot
    robot --test InvalidUserName --loglevel DEBUG login_tests

Run ``robot --help`` for more information about the command line usage and see
`Robot Framework User Guide`_ for more details about test execution in general.



Overview:

It's main use is to enable writing acceptance tests with a high level of abstraction for software products.

The framework requires less technical skill than programming language-based frameworks, and so can be used by team members who have very little programming experience. For example, an agile team product owner could express acceptance tests using the framework, without having to know the details of how the product is implemented.
On the other hand, because of its keyword-based design, those with a high degree of technical skill can write keywords in their language of choice to test low level functions, and even do unit and integration testing if so desired.

Uses:

Because of its flexibility, robot framework can be used to test desktop applications, web applications, mobile applications, and RESTful and SOAP-based services. Because it provides an abstraction layer on top of the physical implementation of the system under test, it is possible to write tests that work cross-platform (ie: the same test case could be used to test both an android and iOS app, or for testing a web app that runs on chrome, firefox and safari).
Although robot framework is often used to test browser-based applications, it has been used to test databases, mobile devices, calculators, and many other things.

Extensibility:

One of the great strengths of the robot framework is that it is highly extensible. Many of the features mentioned above are implemented as libraries. For example, you can plug in a library to use selenium to drive a browser. You can plug in a database library to directly access databases. There are libraries to support testing desktop apps, services, and many more.

Example
To illustrate how abstract a robot test case can be, a BDD-style testcase might look -- literally -- like this:

Given I am on the application login screen
When I enter a valid username and password
And I press the "login button"
Then I should be logged in
And my personal dashboard should be displayed

Note: this isn't the only way to write a test. Robot is very flexible, allowing you to choose between BDD (Behavior Driven Development) style, a traditional procedural style, or in a data-driven style.

The framework provides the infrastructure for converting those statements to actionable items. Ultimately they get boiled down to a function call -- either from an external library, or one provided by the development team. Those functions typically are written in python, but can be written in Java, a .NET language, or other languages through an interface, depending on how you actually run the test.

Reporting:
In addition to being able to run tests, robot framework provides reports and logs that can be used to visualize the state of the product. Logs provide details of every single keyword and function call, reports show the status of complete suites and test cases, and can provide summary information based on arbitrary tags.




