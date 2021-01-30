
***
## **Essential**

### print

???+ abstract ""
    **print AnyType;**

    !!! info ""
        * Prints any valid value **without newline**.
        * **No curved brackets**.

    !!! tip "Example"
            ```
            let a = "Hello"
            let b = " There"
            print a;
            print b;
            // Output: Hello There
            ```

***
### println

???+ abstract ""
    **println AnyType;**

    !!! info ""
        * Prints any valid value **with newline**.
        * **No curved brackets**.

    !!! tip "Example"
            ```
            let a = "Hello"
            let b = " There"
            println a;
            println b;
            // Output: Hello
            //          There
            ```

***
### bai

???+ abstract ""
    **bai AnyType;**

    !!! info ""
        * Exits Ari prematurely and prints out the given value.
        * **No curved brackets**.

    !!! tip "Example"
            ```
            let something = 1 / 999;
            bai "The program has ended. Nothing to see here."; // Exit program
            println "Nothing is impossible"; // This will never print
            ```

***
## ** Random generation **

### random_choose

???+ abstract ""
    **random_choose(source: [Array](../array), number_of_elements: [Number](../number))** ➟ **[Array](../array)**

    !!! info ""
        * A [uniform distribution](https://en.wikipedia.org/wiki/Discrete_uniform_distribution) is used to randomly select an element from the [source](../array).
        * The number of elements determine the length of the generated array and must be zero or positive.

    !!! tip "Example"
        * This example simulates 1000 throws of a fair dice:
            ```
            println random_choose([1, 2, 3, 4, 5, 6], 1000); // 1000 random values
                                                             // [2, 3, 4, 5, 2,  ...]
            ```

***
### random_normal

???+ abstract ""
    **random_normal(mean: [Number](../number), standard_deviation: [Number](../number), number_of_elements: [Number](../number))** ➟ **[Array](../array)**

    !!! info ""
        * A [normal distribution](https://en.wikipedia.org/wiki/Normal_distribution) is used to generate an array of random values using the [mean](../number) and [standard_deviation](../number).
        * The number of elements determine the length of the generated array and must be zero or positive.

    !!! tip "Example"
        * This example generates 1000 samples with zero mean and a standard deviation of 1:
            ```
            println random_normal(0, 1, 1000); // 1000 random values
                                               // [0.3446016, -0.2162096, -0.8018565, 0.60348547, 0.42210117,  ...]
            ```

***
## ** File operations **

### read_file

???+ abstract ""
    **read_file(file_path: [String](../string))** ➟ **[Null](../null)**

    !!! info ""
        * Returns the [contents](../string) of a file specified by the [file path](../string).
        * If the file does not exist or cannot be read, [Null](../null) is returned.

    !!! tip "Example"
        * This example introduces a simple error-handling pattern in case the file is not found:
            ```
            let contents = read_file("myfile.txt");
            if (contents == null) {
                println "Failed to read file!";
            }
            else {
                println "Success!";
            }
            ```

***
### write_file

???+ abstract ""
    **write_file(file_path: [String](../string), data: [String](../string))** ➟ **[Number](../number)**

    !!! info ""
        * Writes [data](../string) to a file specified by the [file path](../string). If the file does not exist, a new file will be created.
        Otherwise, the contents of an existing file will be overwritten.
        * If everything goes as planned, the function will return 1.
        * If an error occurs during the writing, the function will return 0.  

    !!! tip "Example"
        * This example introduces a simple error-handling pattern in case the write operation fails:
            ```
            let result = write_file("myfile.txt", "My passwords are ...");
            if (result == 0) {
                println "Failed to write to file!";
            }
            else {
                println "Success!";
            }
            ```

***
## ** Web stuff **

### serve_static_folder

???+ abstract ""
    **serve_static_folder(folder_path: [String](../string), address: [String](../string), port: [Number](../number))** ➟ **Nothing**

    !!! info ""
        * Starts a local web server which serves static files inside the given [folder path](../string).
        * The most convenient [address](../string) is **"localhost"** and the [port](../number) must be a [Number](../number).
        * Similar to how [Express.js](https://expressjs.com/en/starter/static-files.html) does it. More info [here](https://stackoverflow.com/questions/28918845/what-exactly-does-serving-static-files-mean).
        * Press **Control-C** to quit the server.

    !!! tip "Example"
        * This example starts a server at **localhost:8000**
            ```
            serve_static_folder("public", "localhost", 8000);

            // Configured for staging.
            //    => address: localhost
            //    => port: 8000
            //    => log: normal
            //    => workers: 16
            //    => secret key: generated
            //    => limits: forms = 32KiB
            //    => keep-alive: 5s
            //    => read timeout: 5s
            //    => write timeout: 5s
            //    => tls: disabled
            // Mounting /:
            //    => GET / [10]
            //    => GET /<path..> [10]
            // Rocket has launched from http://localhost:8000
            ```

***
### web_get

???+ abstract ""
    **web_get(url: [String](../string))** ➟ **[String](../string)**

    !!! info ""
        * Returns the response of a [GET request](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/GET) from the given [url](../string).
        * Returns [Null](../null) if the request fails.

    !!! tip "Example"
        * This example sends a [GET request](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/GET) to [this website](http://www.blankwebsite.com/) and writes the response to a new HTML file:
            ```
            let content = web_get("http://www.blankwebsite.com/");
            write_file("blank.html", content);
            ```

***
### web_post

???+ abstract ""
    **web_get(url: [String](../string), parameters: [Array](../array))** ➟ **[String](../string)**

    !!! info ""
        * Returns the response of a [POST request](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST) from the given [url](../string).
        * [parameters](../array) must be an array of [Strings](../string)). The elements with even-numbered indexes (0, 2, 4, ...) are regarded as keys,
        whereas elements with odd-numbered indexes (1, 3, 5, ...) are regarded as values.
        * Returns [Null](../null) if the request fails.

    !!! tip "Example"
        * This example sends a [POST request](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST) to [this website](http://httpbin.org/post) with **two parameters** and writes the response to a `response.txt` file:
            ```
            let content = web_post("http://httpbin.org/post", ["key1", "value1", "key2", "value2"]);
            write_file("response.txt", content);
            ```

        * The contents of `response.txt` looks like this:
            ```hl_lines="14 15"
            {
                "args": {}, 
                "data": "{\"key1\":\"value1\",\"key2\":\"value2\"}", 
                "files": {}, 
                "form": {}, 
                "headers": {
                    "Accept": "*/*", 
                    "Content-Length": "33", 
                    "Content-Type": "application/json", 
                    "Host": "httpbin.org", 
                    "X-Amzn-Trace-Id": "Root=1-6013ad21-1cf269b238720911742db09c"
                }, 
                "json": {
                    "key1": "value1", 
                    "key2": "value2"
                }, 
                "origin": "219.95.127.175", 
                "url": "http://httpbin.org/post"
            }
            ```
        
        * **Lines 14** and **15** confirms that the website's server received our [POST request](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST) successfully.
            ```