CFlashmsg
=========

Class CFlashmsg, a class whose purpose is to handle feedback information based on user's actions by means
of flash messages.

By Tomas Vo, tomasvo89@gmail.com


Instructions
------------------

###1. Download

First of all install by using composer. Add this code to your composer.json:

```javascript
"require": {
    "tovo/cflashmsg": "dev-master"
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

For info messages:

```php
    $app->CFlashmsg->addInfo('This is an information message'); 
```
For error messages:

```php
    $app->CFlashmsg->addError('This is an error message'); 
```

For warning messages:

```php
    $app->CFlashmsg->addWarning('This is a warning message'); 
```

For success messages:

```php
    $app->CFlashmsg->addSuccess('This is a success message'); 
```
   
The messages will be saved in the session, call these lines to print out the messages:
    
```php
    $messages = $app->CFlashmsg->printMessage();
    $app->views->addString($messages);
```
###3. Optional

The class is compatible with Font Awesome.
