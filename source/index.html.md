---
title: PHP API Reference

toc_footers:
  - <a href='https://github.com/cloudipsp/'>GitHub Org</a>
includes:
  - checkout
  - order

search: true
---

# Introduction

CloudIPSP PHP SDK is an open source library through which your PHP application can easily interact with the API. That allows you to accept payment with Visa/MasterCard cards on your website. Simply generating payment url, token, form.

# Simple start

> Minimal startup example:

```php
<?php
require 'vendor/autoload.php';

\Cloudipsp\Configuration::setMerchantId(1396424);
\Cloudipsp\Configuration::setSecretKey('test');

$data = [
    'currency' => 'USD',
    'amount' => 1111
];
\Cloudipsp\Checkout::url($data)->toCheckout();
```

**Set the configuration:**

* ```'setMerchantId'``` - Checkout Merchant ID from provider merchant portal.
* ```'setSecretKey'``` - Merchant secret key, if operation is credit you need to set-up ```'setCreditKey'```



