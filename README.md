Download Link: https://assignmentchef.com/product/solved-comp322-assignment-3-how-smart-is-your-pointer
<br>



<h1>Smart Pointer Implementation</h1>

Quoting Wikipedia: ​<em>In computer science, a smart pointer is an abstract data type that simulates a pointer while providing added features, such as automatic memory management or bounds checking. Such features are intended to reduce bugs caused by the misuse of pointers, while retaining efficiency. Smart pointers typically keep track of the memory they point to, and may also be used to manage other resources, such as network connections and file handles. Smart pointers originated in the programming language C++. </em>

In this last assignment, we will try to tackle the implementation of a “smart pointer” in its simplest form.

<strong>Please note that for all the questions, you are responsible of providing the appropriate test code in your main function. The output of your program should reflect clearly the answers for each question. Failing to do so will be penalized. </strong>

<strong>Also note that you need to double check and confirm that your code compiles before submitting to myCourses. The best way to minimize compilation issues on our side, is to provide only one cpp file containing all the code. </strong>




<h1>Question 1</h1>

Research smart pointers provided by the standard library (since C++11). List them and explain the difference between them.




<h1>Question 2</h1>

Design and implement your own smart pointer class called ​<strong>SmartPointer ​</strong>that will automatically delete the memory for built-in integer type that is allocated through it.

SmartPointer class should be used this way in your main() function:

<strong>SmartPointer sPointer(11); </strong>

Here we are passing 11 as an argument to the constructor of SmartPointer class. The constructor will allocate an integer variable and will initialize it to 11.

To get the value of your variable, you should provide and implement a method called getValue(). You use it this way: <strong>cout &lt;&lt; sPointer.getValue(); // prints 11 </strong>

You should also be able to differ the initialization of your allocated int variable to a later moment. For example the following code should be supported as well: <strong>SmartPointer sPointer; sPointer.setValue(133); cout &lt;&lt; sPointer.getValue(); // prints 133 </strong>

Please note that for this question, SmartPointer class will only handle allocation of integer type variables. Allocating arrays is not supported to keep the class simple. No reference counting is required.

The default constructor should allocate and initialize the allocated integer to zero. The destructor should take care of deleting the allocated memory.




<h1>Question 3</h1>

Exceptions are problems encountered during the execution of the program. For example, if the system runs out of memory during a dynamic allocation, it will raise an exception. These exceptions should be treated whenever they are raised in order to avoid the program from yielding undefined behavior or even worse, crashing.

Add appropriate exception handling for the SmartPointer class to treat the following 2 cases:

<ol>

 <li>When allocating a new variable, the code should throw an exception if the system runs out of memory. This exception should be treated and a message should be displayed to the screen warning the user that the variable was not being allocated. I am aware that this cannot really be tested out of the box, so I’m not expecting your main to provide a test case for this situation. However, I want to see that your code “catch” the appropriate exception that the operating system throws when it runs out of memory.</li>

 <li>Let’s assume that we are only interested in positive numbers. The code should throw an exception whenever a user tries to assign a negative number to any variable that was being allocated through SmartPointer class. This exception should be treated and a message should be displayed to the screen warning the user that the class does not handle negative numbers.</li>

</ol>




<h1>Question 4</h1>

Make the class SmartPointer generic using templates to be able to allocate any built-in type through it (int, float, double). Let’s ignore char and string types for simplicity.

Use case:

<strong>SmartPointer&lt;float&gt; sPointer; sPointer.setValue(13.31); cout &lt;&lt; sPointer.getValue(); </strong>




<h1>Question 5</h1>

Overload the operators +, – and * to be able to perform arithmetic operations on variables allocated through SmartPointer class. Don’t use member methods for the overloaded functions, use friend functions instead. These overloaded functions should be generic as well (using templates).

Use case:

<strong>SmartPointer&lt;float&gt; sPointer1; </strong>

<strong>sPointer1.setValue(1.5); </strong>

<strong> </strong>

<strong>SmartPointer&lt;float&gt; sPointer2; sPointer2.setValue(2.5); </strong>

<strong> </strong>

<strong>SmartPointer&lt;float&gt; sPointer3 = sPointer1 + sPointer2; cout &lt;&lt; sPointer3.getValue() &lt;&lt; endl; // prints 4 </strong>




<h1>Question 6</h1>

How can you adapt the class SmartPointer to be able to handle allocation of arrays? Please provide a full implementation. Feel free to choose any suitable signature for your class, including the way it should be used.

Note that the same class should now handle both cases, the array case and the single variable case. You should not provide two separate implementations to handle these 2 cases.

You should also add the use case in the main function.