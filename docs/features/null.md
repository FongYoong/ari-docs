
* [Null](../null) is a placeholder value to represent "nothingness".

!!! warning "Warning"
    Arithmetic does not apply to [Null](../null). Cannot use [Null](../null) with [Number](../number) or [String](../String).

***
## ** Logical operators **

| Operator   | Description  |
| :--------: | :---------:  |
| `!`        |   Not        |
| `==`       | Equal to     |
| `!=`       | Not equal to |
| `and`      | And          |
| `or`       | Or           |

!!! info "Info"
    * Logical operators are similar to that of [Boolean](../boolean).
    * However, `and` and `or` will always return [Null](../null).

!!! warning "Warning"
    * Ordered comparisons such as `>` or `<` do not work for [Null](../null).

!!! example "Example"

    === "REPL.IT"

        <iframe height="400em" width="100%" src="https://repl.it/@FongChien/Null-1?lite=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

    === "Code only"

        ```
        println null == null;   // true
        println null != null;   // false
        println null and null;  // null
        println null or null ;  // null
        println null == false;  // Error because Null cannot be compared with Boolean
        ```

***
