# Variables and Data Types 
* **variables** - labeled containers that hold data
    - should start with `$`
    ```php
    $name = "Jake"; // name is a string
    $age = 23; // age is a int
    $money = "200.32"; // money is a float
    $student = true; // student is a boolean
    $schoolMates = ["Mary", "Jackson", "Mark"]; // schoolmates is an array 
    $parents = array("Dad" => 56, "Mom" => 52); // associative array
    ```

# Expressions and Operators
* **expressions** - like a math equation it always results in something
    - anything that has `value`
    ```php
    $biggerMoney = $yourMoney < $myMoney
    ```

* **operators** - tools in performing actions on data
    - these symbols are used to perform `operations`
    - they take 1 or more arguments
    ```
    + -> addition
    - -> subtraction
    * - multiplication
    / - division
    % - modulo

    += -> add then assign
    -= -> subtract then assign

    ++ -> increment by one
    -- -> increment by one

    // Logical operators
    && -> and operator
    || -> or operator
    <= -> less than or equal to
    >= -> greater than or equal to
    == -> equal to (weak check, w/o type check)
    === -> strictly equal to (strong check, w/ type check)
    ```

# Control Structures
* **if else** - decision based on whether something is true
    ```php
    if ($money > 300) { // this is a comparison expression
        echo "You're rich!";
    } else {
        echo "You're poor!";
    }
    ```
    ```php
    if ($money > 300) { // this is a nested comparison expression
        echo "You're rich!";
    } else if ($money === 200.32 ) { // strict type checking
        echo "Exact money";
    } else {
        echo "You're poor!";
    }
    ```
* **ternary** - shortcut to the same decision
    ```php
    echo ($money > 300 ? "You're rich" : "You're poor"));
    ```
    ```php
    // nested ternary
    echo ($money > 300 ? "You're rich" :
    (($money == 200.32) ? "Exact money" 
                       : "You're poor"));
    ```
* **switch** - menu where you have a list of options
    - NOTE: Can do more than just one without a break statement
    ```php
        switch ($user_input) {
            case '1':
                echo "The fare is 12 pesos<br/>";
                break;
            
            case '2':
                echo "The fare is 14 pesos<br/>";
                break;
            
            case '3':
                echo "The fare is 16 pesos<br/>";
                break;
            
            default:
                echo "The fare is 18 pesos<br/>";
                break;
        };
    ```
* **match** - precise options like with a key and lock
    - strict conditional statement 
    ```php
        $fare = match($user_input) {
            1 => "The fare is 12 pesos<br/>",
            2 => "The fare is 14 pesos<br/>",
            3 => "The fare is 16 pesos<br/>",
            4 => "The fare is 18 pesos<br/>",
        };
    ```
# Control Flow
* **while** **loops** - doing something until you get tired
    - loops until condition is met
    ```php
    while($tired < 10) {
        <!-- action here-->
        $tired++
    }
    ```
* **do** **while** - do something once and whether you want to do it again
    - does expression once and will loop until condition is met
    ```php
        // create or do something first
        do {
            <!--action here-->
            $tired++
        } while($tired < 10)
    ```

* **for loop** - count the amount of times you need to do something
    - loops until condition is met
    ```php
    for ($tired = 0; $tired < 10; $tired++) {
        <!--action here-->
    }
    ```
* **foreach** - going through a pile of books until you finish all of them
    - loops until array
    ```php
    $fares = array(12, 14, 16, 18);

    foreach ($fares as $value) {
        echo $value."Price for ??<br/>";
    }
    ```

    ```php
    $fares = array(
        "Senior" => 12, 
        "Student" => 14,
        "Unemployed" => 16,
        "Employed" => 18
    );

    foreach ($fares as $key => $value) {
        echo $value . " Price for $key<br/>";
    }
   ```

# Functions
* **define** **&** **call** **functions** - recipe to create or do something
    - start with keyword function
    ```php
    function greeting(): void {
        echo "Hello";
    }
    
    greeting();
    ```

* **get data from function** - after finishing you give to the person
    - return something 
    ```php
    function stringOrInt(): string|int {
        return 20.38;
    }
    $funcVal = stringOrInt();
    ```
* **defining functions that needs data** - ingredients for the recipe
    - parameters for function
    ```php
    $myAge = 21;
    function squareNum($num) {
        return $num * $num;
    }

    $squaredNum = squareNum($myAge);
    echo "My squared age is $squaredNum";
    ```
* **specify data types** - specifying what type of sugar you need, brown, white etc.
    - in functions to easily know what it needs
    ```php
    $myAge = 21;
    function squareNum(int $num): int {
        return $num * $num;
    }

    $squaredNum = squareNum($myAge);
    echo "My squared age is $squaredNum";
    ```

* **optional** - these are ingredients that are not necessarily needed but could help with the taste
    - you can either pass the value or not
    ```php
    $myAge = 21;
    function squareNum(?int $num = null): int {
        if (num === null) {
            return 1;
        }
        return $num * $num;
    }

    $squaredNum = squareNum($myAge);
    echo "My squared age is $squaredNum";
    ```

* **default value** - backup ingredient, vegetable oil instead of olive oil
    - default material for a floor is wood, but could be tiles
    ```php
    $myAge = 21;
    function squareNum($num = null): int {
        if (num === null) {
            return 1;
        }
        return $num * $num;
    }
    ```

# File Inclusion
* **include** - inviting a friend to come to your birthday
    - You'll feel like someone is missing but you can still continue
    ```php
    <?php include "footer.php"?>
    ```
* **require** - inviting a priest to come to your wedding
    - if file is not found then it will error
    - importing a file into your current file
    ```php
    <?php require "footer.php"?>
    ```
