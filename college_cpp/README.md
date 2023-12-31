# Before You Read

> **This is not a comprehensive guide。**
>
> Topics Covered：[Basic IO operations, Conditionals and Loops, Opertors, Array, Strings, Pointers and Classes]
>
> Prepared By : [Arjun Gautam (22070123043)]

### Section 1: Basic IO Operations

> How to get User Input in C++
>
> 1. istream is used for inputs, to access it use iostream header.
> 2. istream has overloaded the right bit shift operator, so to do inputs right operand of ">>" operator must be an istream object.
> 3. std::cin >> age (This code will store whatever is entered in input stream to age variable assuming the input entered is appropriate for the type of the variable)
>
> How to print things to output stream
>
> 1. ostream is used for outputs, to access it use iostream header.
> 2. ostream has overloaded the left bit shift operator, so to do outputs right operand of "<<" operator must be an ostream object.
> 3. std::cout << age (This code will print whatever age variable is storing to the output stream)
>
> ![](Images/1.IO/io.png)
>
> Both the istream and ostream objects return their left operand cin and cout respectively, therefore we can chain together multiple input and output expressions.
> eg. std::cin >> age >> gender >> height

### Section 2: Conditionals and Loops

> Loops
> To run a block of code multiple times, we use a loop.
> c++ offers three types of loops: for, while and do while.
> A simple program that demonstrates the use of all three loops:
>
> ![](Images/2.LOOP/loop.png)
>
> for loop has three parts to it.
> The first part is used to create a counter variable
> The second part is to test some condition for executing the loop.
> The third part is to increment or decrement the counter variable.
> In contrast while loop contain just the condition part.
> do while are similar to while except that they'll will execute the code block atleast once.
> loops can be nested, although it is generally a good idea to avoid nesting of loop if it is possible to make code more efficient.
>
> Conditionals are statements that allow a block of code to execute based off some condition.
> let say you want some piece of code to execute only on certain scenarios, you can do that using if statements.
> if statment will execute the code in it's block if the conditon evaluates to a true value.
> ![](Images/2.LOOP/if.png)!
>
> if statements can be coupled with two additionals statements called "else if" and "else"
> To test more than one conditions, we can use else if statments and else statments.

### Section 3: Operators

> There are following Types of opeartors in C++:
>
> 1. Arithmetic Opertors: +, -, \*, /. (note: '/' when used with integer will not keep any decimal part eg/ 2/3: will evauluate to 0)
> 2. Relational Opertors: >, <, >=, <=.
> 3. Bitwise operators: Perform Bitwise operations such as << (left shift), >> (right shift), | (bitwise or), & (bitwise and), ^ (XOR opertor) ~(not operator)
> 4. Logical Operator: logical AND (&&), logical NOT(!), logical OR (||)
> 5. Increment And Decrement Operators: There are two types of those, prefix increment/decrement and postfix increment/decrement, prefix increment (++x), will increase the value of x and the expression evaluates to new value of x whereas postfix(x++), will make a copy of x, increment x and then return the copy (the old x).
>
> ![](Images/3.Operators/operator.png)

### Section 4: Array

> 1. Array is a contiguous block of memory allocated to store data in sequential order.
> 2. Array in C++ can be initialized as follows:
> 3. int numbers[5] = {1, 2, 3, 4, 5}
> 4. Arrays are indexed from 0.
> 5. Elements in an array can be accessed as follows:
>    std::cout << numbers[1]; will print the element at index 1 in the array.
>    ![](Images/4.Array/array.png)

### Section 5: Pointers

> 1. Pointers are variables that memory address.
> 2. Usually we use pointers to store the address of other variables for indirect access of the variable.
> 3. & : this address of operator is used to get the memory address of any variable.
> 4. (\*) : dereference operator: this operator is used to get the value at a given address
> 5. int \*x = &y (this line of code will declare a pointer variable x, which points to the address of the y)
> 6. std::cout << \*x; will print the value stored at the address of y.
> 7. we can use pointers to access elements of an array.
> 8. each element can be accessed iteratively by incrementing the pointer by 1 in each iteration.
>
> ![](Images/5.Pointers/pointer.png)

### Section 6: Strings

>

#### C-Style String

> 1. These are a bit tricky to work with as compared to std::string, they are basically an array of character in which last element of array is a null terminator ('\0')
> 2. C-Style strings can be declared as follows: char str[10] = "ashish"
> 3. Here we need to declare the size of the string+1 for the null terminator character.
> 4. They're fixed in size, they cannot be allocated more memory once created.(simply they cannot be modified)

#### std::string

> 1. These are specific to c++, and are much more convenient way to handle strings.
> 2. They are dynamically allocated, so we don't need to specify the size of string prior to it's declaration.
> 3. They can be modified once created.
> 4. passing std::string as function argument, makes a copy of that string, so it is usually expensive memory wise to pass copies of std::string so it should be avoided.

#### std::string_view

> 1. string_view are similar to std::string but they are read-only
> 2. when we pass these by value to function parameters, they do not make copies.

#### Example of std::string and std::string_view objects

> 1. std::string x {"ashish"};
> 2. std::string_view x {"ashish"};

### Section 7: Classes

> Object Oriented Programming is a paradigm of programming in which we try to model our own types/objects.
> For example we want to write a program for representing a "player" in a game, a player has very specific attributes such as health, attacks, level etc. and a "player" can perform some tasks such as attack, jump, move etc. this can be easily represented using functions and some data structure to store player's attributes. But let say now we want it to be multi-player game, so there would be many such "players" now it becomes a bit more difficult to manage such code, complexity exponentially increases. What if we could bundle together all the code for "Player" together?
> The above problem can be easily solved using Classes and objects, considering the above example we can create a "Player" Class, a blueprint to define a player and then we can instantiate that class to get as many players as we want!

#### Some Terminology:

> 1. Class: Class can be thought of as a blueprint which can be reused to create something multiple times. For example a class to represent an Employee in a company, where we'll have to define some basic properties that all employee's share such as name, age, salary, position etc in a class and then that class can be used to create multiple objects.
> 2. Objects: An object is a instance of a class. To understand we can take an example: Let say we declare a class Employee, now each object of this class will represent a different employee. Objects can be given some initial state using something called constructor which we'll see next.
> 3. Constructor: A constructor is used to give objects some initial state/value which is unique to that object. To extend upon the above example where we had an Employee class, Each employee has some predefined characteristics such as name, age, salary etc. we can use a constructor to start off the state of employee object with some specified values for age, name, salary etc.
> 4. Class Specifiers:
>    - public : members can be accessed from outside the class
>    - private : members cannot be accessed or viewed from outside the class.
>    - protected : members cannot be accessed outside of class, they can be accessed in inherited class.

### Section 8: Data-Structures

> 1.  Linked List
>     Overview
>     A linked list is a linear data structure where elements are stored in nodes, and each node points to the next node in the list. Linked lists provide dynamic memory allocation and efficient insertion and deletion operations.

> Operations
> Insertion: Add a new node at the beginning, end, or at a specific position in the linked list.
> Deletion: Remove a node from the list.
> Traversal: Visit each node in the linked list. 2. Stack
> Overview
> A stack is a linear data structure that follows the Last-In-First-Out (LIFO) principle. Elements are added and removed from the same end, known as the top of the stack. Stacks are often used for managing function calls, undo mechanisms, and parsing expressions.

> Operations
> Push: Add an element to the top of the stack.
> Pop: Remove the top element from the stack.
> Peek: Get the top element without removing it.
> isEmpty: Check if the stack is empty. 3. Queue
> Overview
> A queue is a linear data structure that follows the First-In-First-Out (FIFO) principle. Elements are added from the rear, and removal occurs from the front of the queue. Queues are commonly used in scenarios involving task scheduling, breadth-first search algorithms, and print job management.

> Operations
> Enqueue: Add an element to the rear of the queue.
> Dequeue: Remove an element from the front of the queue.
> Peek: Get the front element without removing it.
> isEmpty: Check if the queue is empty. 4. Min Heap
> Overview
> A min heap is a binary tree-based data structure where the parent node's value is smaller than or equal to its children's values. It is used to efficiently find and remove the minimum element. Min heaps are frequently employed in priority queues, graph algorithms like Dijkstra's algorithm, and heap sort.

> Operations
> Insertion: Add a new element to the heap while maintaining the heap property.
> Extract Min: Remove and return the minimum element from the heap.
> Heapify: Ensure the heap property is maintained after insertion or removal operations.
> Understanding these fundamental data structures is crucial for solving various algorithmic problems and building efficient software applications. The provided implementations serve as foundational examples to further explore and apply these concepts in real-world programming scenarios.
