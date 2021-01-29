
* A [Boolean](../boolean) can be either `true` or `false`.

!!! warning "Warning"
    Arithmetic does not apply to [Booleans](../boolean). Cannot use [Booleans](../boolean) with [Number](../number) or [String](../String).

***
## ** Logical operators **

| Operator   | Description  |   Usage           |
| :--------: | :---------:  | :---------:       |
| `!`        |   Negation   |   ! *Bool*         |
| `==`       | Equal to     | *Bool* == *Bool*  |
| `!=`       | Not equal to | *Bool* != *Bool*  |
| `and`      | And          | *Bool* and *Bool* |
| `or`       | Or           | *Bool* and *Bool* |

!!! info "Info"

    * Logical comparisons return a [Boolean](../boolean).

    * `and` `or` can be chained as many as we like:

    `Bool and (Bool or Bool) and Bool or ...`

!!! warning "Warning"
    Ordered comparisons such as `>` or `<` do not work for [Booleans](../boolean).

!!! example "Example"
    === "REPL.IT"

        <iframe height="400em" width="100%" src="https://repl.it/@FongChien/Boolean-1?lite=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

    === "Code only"

        ```
        println true == true;    // true
        println true != false;   // true
        println true and false;  // false
        println  true or false ; // true
        println true + false;    // Error because Booleans cannot be added
        ```
***
