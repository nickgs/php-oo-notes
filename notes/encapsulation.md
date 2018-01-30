## Encapsulation

The idea of Encapsulation and Abstraction may seem simlar. I'd like to explore this idea and the tools we use to implement them. 

Encapsultion is the process of binding all the data (properties) and behaviors (methods) needed to implement our solution. 

In other words, with encapsultion we can hide details of our implementation to users of our object. 

We will use features of the language such as `public`, `private`, and `protected` to define this visibility. 

For example, what is wrong with the class below:

```php
class Car {
    public $make;

    public function getMake() {
        return $this->make;
    }
    public function setMake(String $m) {
        $this->make = $m;
    }
}
```

If we instantiate this class we can use the object in this following way: 

```
$c = new Car();
$c->setMake("Honda");
$c->make;
```

By giving the user of our Car class direct access to the `$make` property we eliminating the need to user the getter and setter we have defined. This give us less encapsulation of the data and behaviors and allows then to be unbound from each other. 

To keep our data and behaviors bound to each other which will expose a single way for users to access the internal data we would define our class as such: 

```php
class Car {
    private $make;

    public function getMake() {
        return $this->make;
    }
    public function setMake(String $m) {
        $this->make = $m;
    }
}

Do you see the difference?

By making our `$make` property private now only the way for instantiated objects of this class to access this property if through the public setter and getter methods.  




