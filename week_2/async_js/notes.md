Slides : https://projects.100xdevs.com/tracks/async-js-1/Asynchronous-Javascript--Callbacks-and-more-2


# Introduction

    - JavaScript is a single threaded language but it can handle asynchronous operations.
        -Asynchronous operations.
            - I/O operations
            - "Concurrency is about dealing with lot of things at once, 
            - Parallelism is about doing a lot of things at once" 
                https://www.youtube.com/watch?v=oV9rvDllKEg
            - JavaScript is primarily concurrent, not parallel.
            
        - In Sync code : The whole program is one entity which gets executed sequentially.
        - In Async code : The program is divided into multiple entities which get executed in parallel.
            - Think in terms of async snippets and sync snippets in javascript.

        - Call back functions.
            - A function that is passed as an argument to another function and is executed after the other function has finished.

        - JS Architecture for async code
            - Call Stack: Tracks function calls in a LIFO order; functions are pushed when called and popped when completed.
                - LIFO stack gets multiple functions when nested.
            - Web APIs: Browser/Node.js provided features for tasks like network requests, timers, and DOM events.
            - Callback Queue: Holds callbacks waiting for execution after Web APIs complete, processed when the call stack is empty.
            - Event Loop: Monitors the call stack and moves tasks from the callback queue to the call stack when it's empty.





- Callback is always called after long running task of a function : False
    - Only true for async operations where it is defined.


    settimeout(sum, 5s) (5s -> Sum) (Sync)
    Every other function execution is async unless defined otherwise.


# Example, try to understand this

            function callback(a , b){
                return a + b
            }

            function func(callback)
            {
                timeout(() => {}, 5s);
                console.log("Hello");
                callback();
            }

            func(callback);


            surli
                        Callback
                        5s
                        Hello
            utx
                        Hello
                        5s
                        Callback
            correct
                        hello
                        callback
                        5s