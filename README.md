# Textplode API v3
API Client files for Textplode

You first need to create an account at http://www.textplode.com and generate an API key in your user settings

# Example Usage

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
