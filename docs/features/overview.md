

## **Make Ari come alive**

* Once Ari is [downloaded](../../setup/download), either:
    * double-click the file
    
        **or**
    
    * open a command line in the same folder and enter `ari-windows` or `./ari-linux`

* Ari's interface should look like this
    ```
    ‾‾‾‾‾‾‾‾‾
    Ari 0.1.0
    _________

    > 
    ```

### Interpreter mode

* The above interface is called the interpreter mode or more commonly known as [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop).
* Experiment with Ari by typing in Ari-compatible syntax:

    ![Placeholder](img/overview/interpreter.png){: loading=lazy }

### Run a program

* For most practical purposes, it is better to write an Ari program in a separate file.
* For example, if the file's name is called `even_numbers.ari`, open the command line and enter `ari-windows even_numbers.ari` or `./ari-linux even_numbers.ari`

!!! example ""

    * Below is a sample code for `even_numbers.ari` and the result:

        ```
        for(let i = 0; i < 10; i = i + 2) {
            print i + ", ";
        }
        ```

    ![Placeholder](img/overview/run_file.png){: loading=lazy }

***
## Values

* Values are Ari's bread and butter:
    ```
    1;               // Number
    "Good mourning"; // String
    true;            // Boolean
    [1, 2, 3];       // Array of Numbers
    ["abc", "def"]; // Array of Strings
    ```
* Check out the other sections for more info.

## Semicolon

* Never forget to add semicolons behind each statement. I know it is annoying, but consider it a mental discipline, like house chores.
    ```hl_lines="2"
    1 + 2;
    50 + 70  // Missing semicolon!
    19 + 21;
    ```

## Whitespace

* Ari doesn't care about whitespace. How much spacing to use is up to you:
    ```
       3; 2;    2; 3;
       4;   1;1;   4;
        5;        5;
          6;    6;
            7;7;
         
    "I love whitespace";
    ```

## Comments

* Everyone loves to gossip, so comment to your heart's content by adding double slashes, `//`:
    ```
    "Shoplifters will be prostituted";
    // Note to self: Change this misspelling in one year's time when I review this code again.
    // Just kidding.
    ```

## Variable names

* [Variable](../variable) **names** can only contain **numbers**, **alphabets**, and the **underscore** `_`. Also, names **cannot begin** with a number; 
    ```

    ```

## Displaying output





## Loops






## Exiting the program





## Arrays





## Generate random numbers






## Reading and writing to files

No delete operations,  because it's experimental, dont want people to lose their files




## Serve static files in a web server




## GET/POST Requests