# APNS

[![Build Status](https://travis-ci.org/gepo/apns-http2.svg?branch=master)](https://travis-ci.org/gepo/apns-http2)
[![Dependency Status](https://www.versioneye.com/user/projects/57891926c3d40f003caa3071/badge.svg)](https://www.versioneye.com/user/projects/57891926c3d40f003caa3071)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/gepo/apns-http2/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/gepo/apns-http2/?branch=master)
[![Code Coverage](https://scrutinizer-ci.com/g/gepo/apns-http2/badges/coverage.png?b=master)](https://scrutinizer-ci.com/g/gepo/apns-http2/?branch=master)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/gepo/apns-http2/blob/master/LICENSE)

PHP library for sending notifications via Apple Push Notification service (APNS) over HTTP/2.

# Installation

You need curl with http2 support installed on your system before work.

To install it on OS X:
```
brew install curl --with-nghttp2 --with-openssl
brew link curl --force
brew reinstall php56 --with-homebrew-curl
```

 
```
composer require gepo/apns-http2
```

# Usage

```php
<?php

require_once __DIR__ . '/vendor/autoload.php';

$client = new \Apns\Client(__DIR__ . '/certs/apns-dev-cert.pem', true);

$message = (new \Apns\Message())
    ->setDeviceIdentifier('a00915e74d60d71ba3fb80252a5e197b60f2e7743f61b4411c713e9aabd2854f')
    ->setAlert('Test message')
;

$client->send($message);
```
