---
sidebar_position: 1
---

# Core PHP

You can use DevDumper in your PHP code and, you can use the desktop app to see the output of your dumped variables or
objects.

## Install PHP Package

You can install the PHP package from the following command:

```bash
composer require ardagnsrn/devdumper-php
```

## Usage

You can use the `ddump` function to dump your variables or objects to the app. Here is an example of how you can use
DevDumper in your PHP code:

```php
ddump('Hello world!');
ddump(['name' => 'John Doe', 'age' => 25]);
ddump(new MyClass());
ddump('First', 'Second', 'Third');
```

Or you can use `DevDumper` class to dump your variables or objects to the app. Here is an example of how you can use
DevDumper in your PHP code:

```php
use ArdaGnsrn\DevDumper\DevDumper;

$dumper = new DevDumper();
$dumper->dump(...$args);
```

## Example

Here is an example of how you can use DevDumper in your PHP code:

```php
$users = [
    ['name' => 'John Doe', 'age' => 25],
    ['name' => 'Jane Doe', 'age' => 23],
    ['name' => 'Jack Doe', 'age' => 20],
];

foreach ($users as $user) {
    ddump($user); // only first user will be dumped, code will stop here
}
```

## Advanced Usage

You can use the `Client` class to send your payloads to the app. Here is an example of how you can use the `Client`.

```php 
$variable = 'Hello world!';

$payloadFactory = (new \ArdaGnsrn\DevDumper\PayloadFactory())
    ->setPayload(new \ArdaGnsrn\DevDumper\Payloads\ContentPayload($variable))
    ->setPayload(new \ArdaGnsrn\DevDumper\Payloads\ColorPayload('green'));

(new \ArdaGnsrn\DevDumper\Client())->sendPayload($payloadFactory);
```