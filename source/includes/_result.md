# Result

## Server callback url

> Example handling result

```php
<?php
/**
 * Setting up testing configuration
 * All testing details you can find here https://docs.fondy.eu/docs/page/2/
 */
require_once 'configuration.php';
require_once SDK_ROOTPATH . '/../vendor/autoload.php';
/**
 * Getting payment result (server_callback_url)
 * Signature validation example server_callback_url
 * you can get params by yourself, or sdk can got it
 */
try {
    $result = new \Cloudipsp\Result\Result();
    /**
      * or you can build with data parsed by yourself 
      * $result = new \Cloudipsp\Result\Result($_POST, $secretKey, $requestType, true);
    */
    if ($result->getData())
        var_dump($result->getData());
    else
        die('No data');
    } catch (\Exception $e) {
        echo "Fail: " . $e->getMessage();
    }
```
```(array)``` <span class="green">getData()</span> - returns callback.

```(bool)``` <span class="green">isValid()</span> - returns if callback valid (checking signature).

```(bool)``` <span class="green">isApprove()</span> - returns payment successfully include (checking signature).

Result is always returned in request context in the same content-type. So if request is sent in JSON, response will be sent in JSON format too. Response for such request will be interim and will contain URL where customer must be redirected to payment page.

Sending request in interaction scheme A does not assume getting response in request context. Final response will be returned to merchant URL, specified in response_url and server_callback_url Parameters.
