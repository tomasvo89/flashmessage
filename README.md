[![Build Status](https://travis-ci.org/tovo/flashmessage.svg?branch=master)](https://travis-ci.org/tovo/flashmessage)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/tovo/flashmessage/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/tovo/flashmessage/?branch=master)
[![Code Coverage](https://scrutinizer-ci.com/g/tovo/flashmessage/badges/coverage.png?b=master)](https://scrutinizer-ci.com/g/tovo/flashmessage/?branch=master)

CFlashmsg
=========

Class CFlashmsg - a class to handle feedback information based on user's actions by generating
flash messages.

By Tomas Vo, 
tomasvo89@gmail.com


Install instructions
---------------------------

###1. Download

Install by using composer. Add this code to your composer.json:

```javascript
"require": {
    "tovo/flashmessage": "dev-master"
},
```

###2. Include CFlashmsg to your framework

Add this code to your front-controller.

```php
$di->set('CFlashmsg', function() use ($di) { 
    $message = new \tovo\CFlashmsg\CFlashmsg($di);  
    return $message; 
}); 
```

Add the following codes to retrieve flash messages:

For success messages:
```php
    $app->CFlashmsg->addSuccess('This is a success message'); 
```

For error messages:
```php
    $app->CFlashmsg->addError('This is an error message'); 
```

For warning messages:
```php
    $app->CFlashmsg->addWarning('This is a warning message'); 
```

For info messages:
```php
    $app->CFlashmsg->addInfo('This is an information message'); 
```
   
The messages will be saved in the session, call these lines to print out the messages:
    
```php
    $messages = $app->CFlashmsg->printMessage();
    $app->views->addString($messages);
```

###3. Optional

The class is compatible with Font Awesome.
