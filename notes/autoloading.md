## Autoloading

Autoloading is the process of automating how our program finds the files that contain the object implementations it needs to run.

Without autoloading we would do something like this:

```php
<?php

require_once(__DIR__ . "/src/Car.php");

// Now I can contruct a Car!
$c = new Car();
```

A couple of problems arise here:

1. We need to know where the `Car.php` file lives on the filesystem.
2. In a larger project we may have a huge `includes.php` file that handles all of the systems dependenices. For a given object we may not need ALL the includes. 
3. What if our system has two Car definitions both providing different functionality? (this is where namespacing comes into play)

With an autoloader we simply need to have ONE `require_once` in our project and then the class files will be loaded at runtime as we need to them. A quick note, here is a [good write up on the performance impacts of this.](https://blog.ircmaxell.com/2012/07/is-autoloading-good-solution.html)

For example:

```php
<?php

require_once(__DIR__ . "/autoloader.php");

$c = new Car();
$o = new Order();

```

## Namespaces

Support for namespaces was included in PHP 5.3. Namespaces solve 2 core problems for us: 

1.  Avoid naming collisions with other class names and/or method names. This could be between code you write and third party code you bring into the project. 
2. Give us the ability to alias class names to be a bit more succicnt in our code if we choose to.

We can think of a namespace as a safe place for us to develop our own set of names without having to worry about the "outside world". We could think of this as a type of encapsulation. One our our OO pillars! 

What does this look like?

```php
<?php

//declare our classes namespace
namespace Vehicles;

class Car {
	// ...
}
```
In this example, our Car lives in the `\Vehicles` namespace. Now with in any other class that uses this we can declare that we do so with the `use` keyword. For example: 

```php
<?php
require_once(__DIR__ . "/autoloader.php");

use \Vehicles\Car;

$c = new Car();
```
##Autoloading standards

##PSR-4
PHP Standards Recommendations, PSR's, are recommendations put out by the  [PHP Framework Interop Group](http://www.php-fig.org/).

One of these standard recommendations is the [`PSR-4`](http://www.php-fig.org/psr/psr-4/). This recommendation defines a spec for autoloading classes from file paths. 

It basically defines how we should organize our file system to the namespaces we define.  


