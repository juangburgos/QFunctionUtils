# QFunctionUtils

Provides the following helper functions:

* `QFunctionUtils::Debounce` : 

Receives a callback as first argument and a delay time in miliseconds as a second argument. 

Returns an `std::function` with the same signature as the given callback. The returned function
can be called any number of times wihtin the given delay time, but will only execute the 
given callback once the delay time has passed, and the function has not been called in this
period.

This is useful in situations when it is desired to execute a command every so often. For example
when a user clicks a button many times within a short period of time, but the logic behind takes
some time to execute, so it is desired to ignore the multiple clicks and execute the logic 
only once. But if the delay time period passes, then the user can issue the command once again.

* `QFunctionUtils::Throttle` : 

Same as `Debounce`, but it also executes the command once at the beginning, then waits for the
delay time period (ignoring any other of the calls) and then execute it once again at the end 
of the delay time period.

