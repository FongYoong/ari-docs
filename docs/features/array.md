
* A [Array](../array) is a collection or sequence of values of the following types: [Number](../number), [String](../string), [Boolean](../boolean), [Null](../null), [Function](../function), or [Array](../array).

* The array's elements must be of the **same type**.

## **Declaration**

* Below are valid arrays:

    ```
    let a = [1, 2, 3]; // Array of Numbers
    let b = ["abc", "def"]; // Array of String
    let c = [true, false, true]; // Array of Booleans
    let d = []; // Array with zero elements and no particular type
    ```

* Arrays can be nested as deep as we like, as long as the types for each dimension are the same. The length of each nested array **need not** be the same.

    ```
    let d = [[1, 2, 3], [9, 4], [5, 7, 3, 0.25]]; // 2D Array of Numbers
    let e = [[1, 2, 3, 4], ["hoho", "haha", "hehe"], [true, false]]; // 2D Array of mixed types
    let f = [[1, 2, 3], [[5, 5, 5], [8, 8, 8]], [true, false]]; // Multi-dimensional Array with mixed lengths
    ```

!!! warning "Always check the elements' type:"
    * It cannot be emphasised enough that an array's elements **must** have the **same type**.
    * However, arrays are **allowed** to contain **nested arrays of different types**, as demonstrated in the earlier examples.

***
## **Access**

* Add a pair of square brackets [...] and specify an **index** inside the brackets to access the index's value.
* The index of the first element is 0.
* Otherwise, the index must be a positive integer.

    ```
    let a = [7, 8, 9];
    println a[0];               // 7
    println a[0] + a[1] + a[2]; // 24
    ```

!!! warning "Be careful with indexes:"

    * The index must be less than the array's length.

    * **Line 2** below yields an error because the index is out of bounds:

        ```hl_lines="2"
        let a = [7, 8, 9];  // Array of length 3 with indexes 0, 1, and 2
        println a[3];       // Error because index 3 does not exist in the array
        ```

***
## **Assignment**

* Similar syntax to [accessing arrays](../array#access) and [assigning variables](../variable#assignment).

    ```hl_lines="2"
    let a = [1, 2, 3];
    a[0] = 5;   // Change first element to 5
    println a;  // [5, 2, 3]
    ```

!!! warning "Again, be careful with indexes:"

    * The index must be less than the array's length.

    * **Line 2** below yields an error because the index is out of bounds:

        ```hl_lines="2"
        let a = [7, 8, 9];  // Array of length 3 with indexes 0, 1, and 2
        a[3] = 5;           // Error because index 3 does not exist in the array
        ```

***
## ** Arithmetic **

### **Number Arrays**

| Operator   | Description |
| :--------: | :---------: |
| `+`        | Addition    |
| `-`        | Subtraction |
| `*`        | Multiply    |
| `/`        | Divide      |

* [Number arithmetic](../number#arithmetic) is applied element-wise, provided that:
    * [x] both arrays' elements are all [Numbers](../number)
    * [x] both arrays have the **same length/number of elements**. 

!!! warning "Do not take arithmetic for granted:"

    * The line below yields an error due to different array lengths:

        ```
        println [1, 2, 3] + [4, 5, 6, 7]; // Error due to different lengths
        ```

    * Also, division by zero in any of the elements will result in an error.

!!! example "Example 1"

    === "REPL.IT"

        <iframe height="400em" width="100%" src="https://repl.it/@FongChien/Array-1?lite=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

    === "Code only"

        ```
        let a = [1, 2, 3];
        let b = [10, 20, 30];
        let c = [5, 25, 0];
        println a + b; // [11, 22, 33]
        println c - b; // [-5, 5, -30]
        println a * c; // [5, 50, 0]
        println a / b; // [0.1, 0.1, 0.1]
        println a / c; // Error due to division by zero at the 3rd element
        ```

***
### **String Arrays**

| Operator   | Description   |
| :--------: | :---------:   |
| `+`        | Concatenation |

* [String concatenation](../string#arithmetic) is applied element-wise, provided that:
    * [x] both arrays' elements are all [String](../string)
    * [x] both arrays have the **same length/number of elements**. 

    ```
    let a = ["Sweet", "Hio", "Anal"];
    let b = [" Home", " Hio", " swab"];
    let c = [" Alabama", " Hio", " test"];
    println a + b + c; // ["Sweet Home Alabama", "Hio Hio Hio", "Anal swab test"]
    ```

***
## ** Logical comparisons **

* Logical operators described in [Number](../number#logical-comparisons), [String](../string#logical-comparisons), and [Boolean](../boolean#logical-operators) are **not supported** out-of-the-box for Arrays.
* We have to manually access each element and compare using [loops](../control_flow#for) or [map](../array#map).
* I apologize for my [laziness](http://gph.is/2dnMUJ6). 

***
## ** Built-in functions **

### length

???+ abstract ""
    **length([Array](../array))** ➟ **[Number](../number)**

    !!! info ""
        * Returns the [Array](../array)'s length.

***
### insert

???+ abstract ""
    **insert(source: [Array](../array), index: [Number](../number), new_value: [Array](../array))** ➟ **[Array](../array)**

    !!! info ""
        * Inserts new_value into the [Array](../array) at the [index](../number) and returns the result.

    !!! example ""
        === "Example"

            !!! tip ""
                ```
                println insert([5, 8, 9], 1, [6, 7]); // [5, 6, 7, 8, 9]
                ```

        === "Warning"
            !!! warning ""
                * [index](../number) must be a **positive integer** and **within the length** of the array.
                * The elements of the inserted array must be of the **same type** as the source.

***
### remove

???+ abstract ""
    **remove(source: [Array](../array), index: [Number](../number))** ➟ **[Array](../array)**

    !!! info ""
        * Removes an element specified by the [index](../number) from the [source](../array) and returns the result.

    !!! example ""
        === "Example"

            !!! tip ""
                ```
                println remove([5, 8, 9], 2); // [5, 8]
                ```

        === "Warning"
            !!! warning ""
                * [index](../number) must be a **positive integer** and **within the length** of the array.

***
### map

???+ abstract ""
    **map(source: [Array](../array), map_function: [Function](../function))** ➟ **[Array](../array)**

    !!! info ""
        * Transforms each element of the array using the given function and returns the result.
        * The mapping [function](../function) must have only **one argument** which represents the array's element.

    !!! example ""
        === "Example"

            !!! tip ""
                ```
                fn do_something (a) {
                    return (a - 5) / 100;
                }
                println map([5, 8, 9], do_something); // [0, 0.03, 0.04]
                ```

        === "Warning"
            !!! warning ""
                * If the [function](../function) returns different types of values, such as [Number](../number) and [String](../string),
                the resulting array may contain elements of different types. Although this violates the [Declaration](../array#declaration) criteria which requires
                elements to be of the same type, it is allowed for the sake of flexibility, but proceed at your own risk.

***
### filter

???+ abstract ""
    **filter(source: [Array](../array), filter_function: [Function](../function))** ➟ **[Array](../array)**

    !!! info ""
        * Each element of the array is fed into the filtering [function](../function) which returns a [Boolean](../boolean). Each element is **retained** if the [Boolean](../boolean) is `true`, and is **excluded** if `false`
        * The filtering [function](../function) **must** return a [Boolean](../boolean).
        * The filtering [function](../function) must have only **one argument** which represents the array's element.

    !!! tip "Example"
        * This example filters out elements greater-or-equal to 5:
            ```
            fn less_than_5 (a) {
                return a < 5;
            }
            println filter([3, 8, 9, 5, 4], less_than_5); // [3, 4]
            ```

***
### reduce

???+ abstract ""
    **reduce(source: [Array](../array), initial_value: [AnyType](), reduce_function: [Function](../function))** ➟ **[AnyType]()**

    !!! info ""
        * At the start, the initial value and the first element of the array is fed into the reducing [function](../function) which does something to the two values and returns a new value. This new value and the next array element are then fed into the reducing function, and the process repeats until the end of the array. The final resulting value is returned.
        * The initial value must be of the **same type** as the array's elements.
        * The filtering [function](../function) must have only **two arguments**, the left argument represents the initial/previous value and the right argument represents the current element of the array.

    !!! tip "Example"
        * This example returns the sum of the first 10 integers. Note that the initial value is 0:
            ```
            fn sum (a, b) {
                return a + b;
            }
            println reduce([1, 2, 3, 4, 5, 6, 7, 8, 9, 10], 0, sum);
            // 55
            ```

***
### range

???+ abstract ""
    **range(start: [Number](../number), end: [Number](../number), step: [Number](../number))** ➟ **[Array](../array)**

    !!! info ""
        * Returns a [Number](../number) array containing values within the specified **start**, **end**, and **step**.

    !!! example ""

        === "Example"

            !!! tip "Example"
                * This example returns numbers between 1 to 3 with a step of 0.5:
                    ```
                    println range(1, 3, 0.5);
                    // [1, 1.5, 2, 2.5, 3]
                    ```

        === "Warning"

            !!! warning ""
                * The step **cannot be zero** unless the start and end are the same.
                * If the numbers are **increasing**, the step must be **positive**.
                * If the numbers are **decreasing**, the step must be **negative**.

***
### linspace

???+ abstract ""
    **linspace(start: [Number](../number), end: [Number](../number), number_of_elements: [Number](../number))** ➟ **[Array](../array)**

    !!! info ""
        * Returns a [Number](../number) array containing values within the specified **start**, **end**, and **number_of_elements**.
        * Obviously, the number of elements must be zero or positive.


    !!! tip "Example"
    * This example returns 5 numbers between 1 and 3:
        ```
        println linspace(1, 3, 5);
        // [1, 1.5, 2, 2.5, 3]
        ```

***
### repeat

???+ abstract ""
    **repeat(value_to_repeat: [AnyType](), number_of_elements: [Number](../number))** ➟ **[Array](../array)**

    !!! info ""
        * Returns an array containing repeated copies of the same value.
        * Obviously, the number of elements must be zero or positive.

    !!! tip "Example"
    * This example returns numbers between 1 to 3 with a step of 0.5:
        ```
        println repeat(2.5, 1000); // 1000 values of 2.5
                                   // [2.5, 2.5, 2.5, 2.5, ...]
        ```