---
title: API Reference

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/cloudipsp/'>Git</a>

includes:
  - errors

search: true
---

# Introduction

PHP SDK future docs

# Start

> Minimal startup example:

```php
require 'vendor/autoload.php';

\Fondy\Configuration::setMerchantId(1396424);
\Fondy\Configuration::setSecretKey('test');

$data = [
    'currency' => 'USD',
    'amount' => 1111
];
Fondy\Checkout::url($data)->toCheckout();
```

