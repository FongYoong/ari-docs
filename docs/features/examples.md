

***
## Estimating Pi, **π**, with Monte Carlo

* Check out page 3 of [this document (PDF)](https://arxiv.org/ftp/arxiv/papers/1909/1909.13212.pdf) for more info.

!!! example ""

    === "REPL.IT"

        <iframe height="400em" width="100%" src="https://repl.it/@FongChien/Example-Monte-Carlo?lite=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

    === "Code only"

        ```
        let number_of_iterations = 25;
        let number_of_samples = 500;
        let radius = 200;
        let radius_squared = power(radius, 2);
        let sample_space = linspace(0, radius, 10000);
        let pi = 0;

        for(let i = 0; i < number_of_iterations; i = i + 1) {
            let x_array = random_choose(sample_space, number_of_samples);
            let y_array = random_choose(sample_space, number_of_samples);

            let count = 0;
            for(let k = 0; k < number_of_samples; k = k + 1) {
                let distance_squared = power(x_array[k], 2) + power(y_array[k], 2);
                if (distance_squared <= radius_squared) {
                    // Inside circle
                    count = count + 1;
                }
            }
            pi = pi + count / number_of_samples;
            println 4 * pi /number_of_iterations;
        }
        ```
***
## Using FFT for polynomial multiplication

* The [Fast Fourier Transform (FFT)](https://en.wikipedia.org/wiki/Fast_Fourier_transform) can be used to compute the resulting polynomial coefficients of a polynomial multiplication.
* Refer to [this StackExchange answer](https://math.stackexchange.com/a/764870).

!!! example ""

    === "REPL.IT"

        <iframe height="400em" width="100%" src="https://repl.it/@FongChien/Example-FFT?lite=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

    === "Code only"

        ```
        
        ```