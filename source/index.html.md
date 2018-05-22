---
title: PHP API Reference

toc_footers:
  - <a href='https://github.com/cloudipsp/'>GitHub Org</a>
includes:
  - checkout

search: true
---

# Introduction

CloudIPSP PHP SDK is an open source library through which your PHP application can easily interact with the API. That allows you to accept payment with Visa/MasterCard cards on your website. Simply generating payment url, token, form.

# Getting checkout url with minimal settings

> Minimal startup example:

```php
<?php
require 'vendor/autoload.php';

\Fondy\Configuration::setMerchantId(1396424);
\Fondy\Configuration::setSecretKey('test');

$data = [
    'currency' => 'USD',
    'amount' => 1111
];
Fondy\Checkout::url($data)->toCheckout();
```

#### Set the configuration:

* ```'setMerchantId'``` - Checkout Merchant ID from provider merchant portal.
* ```'setSecretKey'``` - Merchant secret key, if operation is credit you need to set-up ```'setCreditKey'```



