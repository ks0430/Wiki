# PHP Wiki

> Author: Evelyn Chu
>
> Start time: 28.09.18
>
> Description: Give some useful php skills

[TOC]



## Classes and Objects



## Normal Methods

This methods are usually used in script, keep it in mind.

### var_dump()

> This function displays structured information about one or more expressions that includes its type and value. Arrays and objects are explored recursively with values indented to show structure.
>

**Input:**

```php
<?php
$a = array(1, 2, array("a", "b", "c"));
var_dump($a);
?>
```

**Output:**

```shell
array(3) {
  [0]=>
  int(1)
  [1]=>
  int(2)
  [2]=>
  array(3) {
    [0]=>
    string(1) "a"
    [1]=>
    string(1) "b"
    [2]=>
    string(1) "c"
  }
}
```

### isset()

> Determine if a variable is set and is not NULL.
> [time=Thu, Sep 27, 2018 1:03 PM]

Same as `if(variable == null)`

```php
$a = "test";
$b = "anothertest";

var_dump(isset($a));      // TRUE
var_dump(isset($a, $b)); // TRUE
unset ($a);

var_dump(isset($a));     // FALSE
var_dump(isset($a, $b)); // FALSE
```

### get_class()

> get_class — Returns the name of the class of an object
> [time=Thu, Sep 27, 2018 1:03 PM]

**Input**

```php
<?php

class foo {
    function name()
    {
        echo "My name is " , get_class($this) , "\n";
    }
}

// create an object
$bar = new foo();

// external call
echo "Its name is " , get_class($bar) , "\n";

// internal call
$bar->name();

?>
```

**Output**

    Its name is foo
    My name is foo



