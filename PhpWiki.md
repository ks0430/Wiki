# PHP Wiki

> Author: Evelyn Chu
>
> Start time: 28.09.18
>
> Description: Give some useful php skills

[TOC]

## Types

### Arrays

An [array](http://php.net/manual/en/language.types.array.php) in PHP is actually an ordered map. A map is a type that associates *values* to *keys*. This type is optimized for several different uses; it can be treated as an array, list (vector), hash table (an implementation of a map), dictionary, collection, stack, queue, and probably more. As [array](http://php.net/manual/en/language.types.array.php) values can be other [array](http://php.net/manual/en/language.types.array.php)s, trees and multidimensional [array](http://php.net/manual/en/language.types.array.php)s are also possible.

#### 1. Defination

As of PHP 5.4 you can also use the short array syntax, which replaces *array()* with *[]*.

```php
<?php
$array = array(
    "foo" => "bar",
    "bar" => "foo",
);

// as of PHP 5.4
$array = [
    "foo" => "bar",
    "bar" => "foo",
];
?>
```

#### 2. Type Casting and Overwriting

**Input:**

```php
<?php
$array = array(
    1    => "a",
    "1"  => "b",
    1.5  => "c",
    true => "d",
);
var_dump($array);
?>
```

**Output:**

```
array(1) {
  [1]=>
  string(1) "d"
}
```



#### 3. Indexed arrays without key

**Input:**

```php
<?php
$array = array("foo", "bar", "hello", "world");
var_dump($array);
?>
```

**Output:**

```
array(4) {
  [0]=>
  string(3) "foo"
  [1]=>
  string(3) "bar"
  [2]=>
  string(5) "hello"
  [3]=>
  string(5) "world"
}
```

#### 4.  Creating/modifying with square bracket syntax

```php
<?php
$arr = array(5 => 1, 12 => 2);

$arr[] = 56;    // This is the same as $arr[13] = 56;
                // at this point of the script

$arr["x"] = 42; // This adds a new element to
                // the array with key "x"
                
unset($arr[5]); // This removes the element from the array

unset($arr);    // This deletes the whole array
?>
```





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

### Print_r()

print_r — Prints human-readable information about a variable.

**Input:**

```php
<?php
$a = array ('a' => 'apple', 'b' => 'banana', 'c' => array ('x', 'y', 'z'));
print_r ($a);
?>
```

**Output:**

```php
Array
(
    [a] => apple
    [b] => banana
    [c] => Array
        (
            [0] => x
            [1] => y
            [2] => z
        )
)
```



