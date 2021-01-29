
* [Control flow](../control_flow) is essential for implementing any computable algorithm. It dictates how the program should proceed from one step to another and enables it to have multiple paths.

***
## **if**

* ```if``` requires an expression which evaluates into a [Boolean](../boolean). This expression must be placed inside a pair of curved brackets:
    
    ```
    if( expresssion )
    ```

!!! warning "An error occurs if the expression does not result in a Boolean"
    ```hl_lines="1 3"
    if(1 + 2) // Invalid because Number
    if(true != false) // Valid
    if("true") // Invalid because String
    if(1 > 2) // Valid
    ```

    * **Lines 1** and **3** are **invalid** because their expressions do not result in a [Boolean](../boolean).

* A pair of curly brackets **must** be placed after the `if` to indicate a new [block scope](../variable#block-scoping-and-shadowing).
* The space inside the curly brackets has a new scope as explained [here](../variable#block-scoping-and-shadowing).
    
    ```hl_lines="3"
    // Outer scope
    if (expression) {
        // Inner scope
    }
    ```

* Statements in the inner scope will only execute **if** the expression's [Boolean](../boolean) is **true**.

    ```
    let a = 90;
    if (a < 100) { // true
        a = a / 3;
    }
    if (a < 40) { // true
        a = (a + 20) / 10;
    }
    if (a < 5) { // false
        a = "Success";
    }
    println a; // 5
    ```

***
## **else**
* What if we want to do something else if the ```if``` expression is **false**?
* Of course, we can add the [negation operator](../boolean#logical-operators) to the expression:

    ```hl_lines="6"
    let a = 5;
    let b = 10;
    if (a + b < 15) { // false
        println "Less than 15";
    }
    if (!(a + b < 15)) { // Negation produces a true value
        println "Not less than 15"; // This gets printed
    }
    ```
* The above approach would be tedious and makes the code look unnecessarily verbose.
* The ```else``` keyword offers a shortcut for this:

    ```hl_lines="6"
    let a = 5;
    let b = 10;
    if (a + b < 15) { // false
        println "Less than 15";
    }
    else { // true
        println "Not less than 15"; // This gets printed
    }
    ```

!!! failure "Warning"
    * Both ```if``` and ```else``` require the curly brackets and an error occurs if otherwise.
    * Although permitted in some popular languages, the syntax below is **not supported** to avoid confusion:
    ```
        if (a + b < 15)
            println "Less than 15";
        else
            println "Not less than 15"; // This gets printed
    ```
    * The above syntax is unsupported because it can cause unexpected behaviour if used incorrectly.
    Apple's IOS had a security bug in 2014 that resulted because of this syntax being permitted in C++.
    More info [here](https://www.imperialviolet.org/2014/02/22/applebug.html).

***
## **while**

* A ```while``` loop requires an expression and a body (curly brackets) just like ```if```.
* The statements in its body are executed indefinitely until the expression is **false**.
* The program below has an "infinite" loop because it repeats without stopping:

    ```
    let count = 1;
    while(true) {
        println count; // prints indefinitely
        count = count + 1; // increments the value of count
    }
    ```

* We can introduce a value check to bound the loop:

    ```hl_lines="2"
    let count = 1;
    while(count <= 10) { // checks the value of count
        println count; // prints 1 to 10
        count = count + 1; // increments the value of count
    }
    ```

***
## **for**

* A ```for``` loop follows the [traditional format](https://en.wikipedia.org/wiki/For_loop#Traditional_for-loops) where we:
    * [x] declare or initialise a [Variable](../variable).
    * [x] specify an expression which evaluates into a [Boolean](../boolean), just like in ```if``` and ```while```.
    * [x] state how the [Variable](../variable) should be modified.
    * [x] separate the above three with semicolons `;`

!!! tip "Check out this example for a better understanding."
    * The program below prints **even** numbers **starting from 0** and **lesser than 10**.
    ```
    // outer scope
    for(let a = 0; a < 10; a = a + 2) {
        // inner scope
        println a; // 0 2 4 6 8
    }
    ```

    * ```let a = 0``` declares a new [variable](../variable) `a` with the number zero. This [variable](../variable)'s scope is bound to the **inner scope**.
    * ```a < 10``` is checked at the **beginning** of every iteration. The loop **stops** when it is **false**.
    * ```a = a + 2``` modifies the [variable](../variable) `a` at the **end** of every iteration.

***
## **Loop keywords**

* There are two keywords relevant to loops:

### **continue**

* A ```continue``` keyword inside a loop will **skip** all the statements after it and move on to the next iteration.
* The program below does not print anything because ```continue`` skips everything after it.

    ```hl_lines="3"
    let count = 1;
    while(count <= 10) {
        continue;
        println count; // Skipped
        count = count + 1; // Skipped
    }
    ```

* The program below prints 1 to 10, but skips 5 due to the ```continue```:

    ```hl_lines="5"
    let count = 1;
    while(count <= 10) {
        if (count == 5) {
            count = count + 1;
            continue;
        }
        println count; // prints 1 2 3 4 6 7 8 9 10
        count = count + 1;
    }
    ```

***
### **break**

* A ```break``` keyword inside a loop will **exit** the loop.
* The program below does not print anything because ```break`` stops the loop.

    ```hl_lines="3"
    let count = 1;
    while(count <= 10) {
        break; // Quits the loop in the first iteration
        println count; // Never executed at all, not even once
        count = count + 1; // Never executed at all, not even once
    }
    ```

* The program below prints 1 to 4:

    ```hl_lines="5"
    let count = 1;
    while(count <= 10) {
        if (count == 5) {
            count = count + 1;
            break;
        }
        println count; // prints 1 2 3 4
        count = count + 1;
    }
    ```

!!! info "Summary"
    * The main difference between [continue](../control_flow#continue) and [break](../control_flow#break) is that:
        * [x] [continue](../control_flow#continue) **skips** to the next iteration.
        * [x] [break](../control_flow#break) **quits** the loop entirely without considering the next iteration.


