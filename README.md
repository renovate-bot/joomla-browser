## Table of Contents

* [The JoomlaBrowser](#the-joomla-browser)
* [Using the JoomlaBrowser to test Joomla Sites](#using-instructions)
  * [Download](#downlload)

## The Joomla Browser
Joomla Browser with Codeception Module Functionality

## Using Instructions
Update Composer.json file in your project, adding 

### Download

```
"require" : "joomla-browser/codeception": "dev-master"
```
then do a
```
composer update 
```
Finally Make changes in Acceptance.suite.yml add JoomlaBrowser as a Module 

Your original `acceptance.suite.yml`probably looks like:

```yaml
modules:
    enabled:
        - WebDriver
        - AcceptanceHelper
    config:
        WebDriver:
            url: 'http://localhost/joomla-cms3/'     # the url that points to the joomla cms
            browser: 'firefox'
            window_size: 1024x768
            capabilities:
              unexpectedAlertBehaviour: 'accept'
        AcceptanceHelper:
            ...
```

You are asked to remove WebDriver module and change it by the JoomlaBrowser module:

```yaml
    config:
        JoomlaBrowser:
            url: 'http://joomla.box/repos/redmember2/tests/joomla-cms3/'     # the url that points to the joomla installation at /tests/system/joomla-cms
            browser: 'firefox'
            window_size: 1024x768
            capabilities:
              unexpectedAlertBehaviour: 'accept'
            username: 'admin'
            password: 'admin'
        AcceptanceHelper:
            ...
```