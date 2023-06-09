# Assignment 6

In this assignment, you will implement a complete heap-based priority queue.  In addition to the description of your task below, there is thorough documentation in the file `pq.c` describing how each function you'll write should behave.

Your work for this assignment will be limited to the file `pq.c`.  In other files, you are provided with some additional starter code that defines the structures you'll be working with and prototypes functions you'll be using and writing.  *It's important that you don't modify the function prototypes.*  To help grade your assignment, we will use a set of unit tests that assume these functions exist and have the same prototypes that are defined in the starter code.  If you change the prototypes, it will cause the unit tests to break, and your grade for the assignment will likely suffer.  Feel free, however, to write any additional functions you need to accomplish the tasks described below.

## Implement a heap-based priority queue

Your task for this assignment is to implement a heap-based priority queue.  Specifically, in the file `pq.c`, you must define the `struct pq` and implement the following functions:

  * `pq_create()` - allocates and initializes a heap-based priority queue
  * `pq_free()` - frees all memory allocated to a priority queue
  * `pq_isempty()` - should tell the user whether a priority queue is empty
  * `pq_insert()` - should insert an element with a specified priority value and data into a priority queue
  * `pq_max()` - should return the *data* of the first element in a priority queue, maximum priority
  * `pq_max_priority()` - should return the *priority* associated with the first element in a priority queue
  * `pq_max_dequeue()` - should remove the first element from a priority queue and return its data

Here are some specific notes on how the priority queue you'll implement should behave:

  * Your priority queue must be implemented using a heap as the underlying data structure.

  * In the priority queue you implement, *higher* priority values (a.k.a. key(x)) should correspond to elements with higher priority.  In other words, the first element in the priority queue should be the one with the *highest* priority value among all elements in the collection.  For example, your priority queue should return an element with priority value 10 before it returns one with priority value 5.

  * Your `pq_insert()` and `pq_max_dequeue()` functions should both have average runtime complexity *O(log n)*, and your `pq_max()` and `pq_max_priority()` functions should both have average complexity *O(1)*.

  * Your priority queue should not have any memory leaks.

  * In lecture, we discussed how you can implement a heap using an array.  In `dynarray.c` and `dynarray.h`, you are provided with a dynamic array implementation you can use to implement your heap, if you'd like.  In addition to this dynamic array implementation, you may implement any additional helper functions you need to make your priority queue work.

## Testing your work

In addition to the starter code provided, you are also provided with some application code in `test.c` to help verify that your functions are behaving the way you want them to.  In particular, the code in `test.c` calls the functions you'll implement in this assignment, passing them appropriate arguments, and then prints the results.  You can use the provided `Makefile` to compile all of the code in the project together, and then you can run the testing code as follows:
```
make
./test
```
You can see some example output from a correct solution to the assignment in the file `example_output.txt`.

In order to verify that your memory freeing functions work correctly, it will be helpful to run the testing application through `valgrind`.

There is also a more extensive unit test suite for all of the functions you'll write for this assignment included in `unittest.c`.  After running `make`, you can run these unit tests as follows:
```
./unittest
```
There are several unit tests included, and if any unit test failures occur, an error message will be printed out indicating the line number in `unittest.c` from which the failure originated.  There are comments above each test that you can read to more thoroughly understand any given test failure.

## Submission

As always, we'll be using Gradescope. Please submit your pq.c file through Gradescope. 

## Grading criteria

To grade your work, the TAs will use the tests in both `test.c` and `unittest.c`.  Your programs **MUST** compile and run on `flip.engr.oregonstate.edu`, so make sure you have tested your work there before you make your final submission, since a program that compiles and runs in one environment may not compile and run in another.  **Assignments that do not compile on flip will receive a grade of 0.**  If you do not have an ENGR account, you can create one at https://teach.engr.oregonstate.edu/.

The assignment is worth 100 total points, broken down as follows:

* 5 points: `struct pq` defines a heap-based priority queue
* 5 points: `pq_create()` correctly allocates and initializes a heap-based priority queue
* 5 points: `pq_free()` correctly frees all memory associated with a priority queue (no memory leaks!)
* 5 points: `pq_isempty()` correctly determines whether a priority queue contains any elements or not
* 5 points: `pq_max()` correctly returns the data of the element with the *highest* priority value
* 5 points: `pq_max_priority()` correctly returns the *highest* priority value in a priority queue
* 20 points: `pq_insert()` correctly inserts a value into a priority queue with the specified priority and restores the heap property as needed
* 20 points: `pq_max_dequeue()` correctly removes the element with the *highest* priority from a priority queue and returns its value, restoring the heap property as needed
* 10 points: `pq_insert()` and `pq_max_dequeue()` are both *O(log n)*, and `pq_max()` and `pq_max_priority()` are both *O(1)*
* 20 points: assignment readme.txt file providing an explanation in your own words of what your code for each section listed above is doing. 


Note that we will only consider changes to `pq.c` when grading your work.  Changes to other files will be ignored.
