wcx-syslog-module
=================

## Introduction

ZF2 Module for the wcx-syslog library to send Syslog Messages to remote servers directly.

## Instalation

The easiest way is to use composer, just add to your [composer.json](http://getcomposer.org):

```js
"require": {
    "weckx/wcx-syslog-module": "dev-master"
}
```
## Usage

Add the module to your application.config.php. To use simply:

```php
//It's usually better to use the BSD format since it's widely supported
use Wcx\Syslog\Message\Bsd as SyslogMessage;

//Create the message
$message = new SyslogMessage();

//Set basic message values
$message->setPriority(SyslogMessage::PRIORITY_NOTICE)
        ->setFacility(SyslogMessage::FACILITY_USER)
        ->setAppName('wcx-syslog')
        ->setMsg('Test message');

//Send to host 192.168.0.1 using UDP
$message->send('192.168.0.1');
```
