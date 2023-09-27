writeup for coding exercise
(1,2). Algorith assessment => a. The GetFactorial method calculates the factorial of a given number n, and 
b. the FormatSeparators method formats an array of strings with appropriate separators.

[Fact(Skip="Not implemented")] attribute is causing the test cases to be skipped because it explicitly marks them as not implemented. 
To fix this, I have removed the Skip attribute so that the test cases can be executed.

3. Refactor the sparrow issue => In this refactored version, I've used the switch expression to make the GetAirspeedVelocity method more concise and easier to read. 
This eliminates the need for multiple if conditions, resulting in cleaner and more maintainable code.

4. parallel processing issue => 1. BUG -> In the InitializeList method, we are using Parallel.ForEach with an async delegate. 
This can lead to unexpected behavior and might not work as expected. Since Parallel.ForEach blocks until all tasks are completed, 
the use of an async delegate can result in thread starvation.

Fix for above BUG => In the InitializeList method, I've removed the async delegate within the Parallel.ForEach loop since it's not necessary here.

2. Bug -> In InitializeDictionary thechallenge lies in the concurrent nature of the operations, where multiple threads might end up trying to add the same item concurrently.
Fix => In this revised code, I'm counting the number of keys in the concurrentDictionary instead of trying to maintain a separate count variable, as using a separate counter in a concurrent environment can be problematic.

This should ensure that each item is initialized only once and the count accurately reflects the number of items initialized
