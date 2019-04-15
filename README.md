# Robotframework
Web testing with Robot Framework and SeleniumLibrary

`Robot Framework`_ is a generic open source test automation framework and
SeleniumLibrary_ is one of the many test libraries that can be used with
it. In addition to showing how they can be used together for web testing,
this demo introduces the basic Robot Framework test data syntax, how tests
are executed, and how logs and reports look like.


Preconditions
-------------

A precondition for running the tests is having `Robot Framework`_ and
SeleniumLibrary_ installed, and they in turn require
Python_. Robot Framework `installation instructions`__ cover both
Robot and Python installations, and SeleniumLibrary has its own
`installation instructions`__.

In practice it is easiest to install Robot Framework and
SeleniumLibrary along with its dependencies using `pip`_ package
manager. Once you have pip installed, all you need to do is running
these commands::

    pip install robotframework
    pip install robotframework-seleniumlibrary

__ https://github.com/robotframework/robotframework/blob/master/INSTALL.rst
__ https://github.com/robotframework/SeleniumLibrary#installation


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

Using different browsers
------------------------

The browser that is used is controlled by ``${BROWSER}`` variable defined in
`resource.robot`_ resource file. Firefox browser is used by default, but that
can be easily overridden from the command line::

    robot --variable BROWSER:Chrome login_tests
    robot --variable BROWSER:IE login_tests

Consult SeleniumLibrary_ documentation about supported browsers.

.. _Robot Framework: http://robotframework.org
.. _SeleniumLibrary: https://github.com/robotframework/SeleniumLibrary
.. _Python: http://python.org
.. _pip: http://pip-installer.org
