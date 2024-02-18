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

You can also use `ddie` function to dump your variables or objects to the app and stop the code. Here is an example of

```php
ddie('Hello world!');
```


Or you can use `DevDumper` class to dump your variables or objects to the app. Here is an example of how you can use
DevDumper in your PHP code:

```php
use ArdaGnsrn\DevDumper\DevDumper;

$dumper = new DevDumper();
$dumper->dump('First', 'Second', 'Third');
```

### Play With Colors

You can use colors in your dumped variables or objects. Here is an example of how you can use colors in your dumped.

 - **Usable colors:** `green` `orange` `red` `purple` `blue` `gray`
 - **Default color:** `blue`

```php
ddump('Hello world!')->color('red');
```

### Die

You can use `die` method to stop the code after dumping your variables or objects. Here is an example of how you can use

```php
ddump('Hello world!')->die();
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
    ddie($user); // only first user will be dumped, code will stop here
}
```
