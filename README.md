<h1>Textplode API v3</h1>
API Client files for Textplode

You first need to create an account at <a target="_blank" href="http://www.textplode.com">http://www.textplode.com</a> and generate an API key in your user settings.

Documentation can be found at <a target="_blank" href="http://api.textplode.com/docs">http://api.textplode.com/docs</a>

<h2>Examples</h2>
<h3>Send to a Single Recipient</h3>

```php
$textplode = new Textplode('API_KEY');

$textplode->messages->set_from("Textplode");
$textplode->messages->set_message("Hello and welcome to Textplode");

$textplode->messages->add_recipient('440000000000');

$textplode->messages->send();
```

<h3>Send to Multiple Recipients with Merge Data</h3>
```php
$textplode = new Textplode('API_KEY');

$textplode->messages->set_from("Textplode");
$textplode->messages->set_message("Hello {FNAME} {LNAME}. Welcome to Textplode");

$merge_data1 = array( array('{FNAME}', 'Contact'), array('{LNAME}', 'One') );
$merge_data2 = array( array('{FNAME}', 'Contact'), array('{LNAME}', 'Two') );

$textplode->messages->add_recipient('440000000000', $merge_data1);
$textplode->messages->add_recipient('440000000001', $merge_data2);

$textplode->messages->send();
```
