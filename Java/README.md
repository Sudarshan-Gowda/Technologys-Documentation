# Java

Java is a secured, object oriented programming language and it is platform independent. Platform Independent means the code which we written in java can run in any of the platform like windows, Linux & Ubuntu etc.

## 1.1	Basic Concepts:
### 1.1.1	Variable:
Variable is used to store data or value.
•	Static variable 
•	Non static variable

### 1.1.2	Method:
Method is used to implement task or operation. Method name should always starts with small letter followed by camel Case.

Method declarations - method definition - return type
•	Static Method -> can be declared by static keyword 
•	Non static method

### 1.1.3	Object:
Object is an entity which has state & behavior, State represents characteristics & behavior represents functionality.

### 1.1.4	Object Class:
Object class is parent class of all the classes in java by default. It is present in java.lang package

Methods available in Object class are: 
1.	equals() – Gives Generic way to compare objects
2.	hashCode() – Return a hash value this is used to search Objects in  a collection.
3.	toString() – Used to convert sting to object.
4.	wait() – Used in synchronizing thread.
5.	notify() - Used in synchronizing thread
6.	notifyAll() - Used in synchronizing thread
7.	getClass() – It gives more information about object
8.	clone() – Return a new Object that are exactly same as the current object.
9.	finalize() -  method is called just before an object is garbage collected.

### 1.1.5	Class:
Class is a blueprint which includes the members like variables, functions (methods), blocks, and constructor.  Or is a collection of Objects, variables, functions (methods), blocks, and constructor.	

### 1.1.6	Blocks:
Blocks is a set of statements enclosed by curly braces, blocks which is represented by static keyword is called static blocks and blocks which is represented by without any static keyword is called non-static block and static block will be executed during class loading & non static block will be executed during object/instance creation.

### 1.1.7	Constructor:
Constructor is a used to create an instance of the class and also used to initialize non static member. Constructor name should be same as class name.

<b>Default Constructor:</b> Constructor doesn't have any parameter is called Default Constructor.
<b>Parameterized Constructor:</b> Constructor which has specified number of parameter is called is Parameterized Constructor.

### 1.1.8	Type-Casting:
Conversion of one type to another type is called casting and it can be data type casting or class casting. 

##### 1.1.8.1	Up-Casting:  
is casting to a super type. Up-casting is always allowed.

##### 1.1.8.2	Down Casting: 
Down Casting is casting to a subtype. It involves a type check and can throw a class cast exception.

##### 1.1.8.3	Data type casting:   
Conversion of variable from one type to other. Here the value may be lost when large type is converted to a smaller type
 
## 1.2	OOPS Concepts:
### 1.2.1	Inheritance:
Inheritance is a process where one class acquires a property from other class, Class from which properties are inherited is class super class and class to which properties are inherited is called sub-class.

#### 1.2.1.1	Single Level: 
Process where subclass acquires properties from single super class.

#### 1.2.1.2	Multi-Level: 
Process where sub-class acquires properties from super class which intern quires from some other super class.

#### 1.2.1.3	Multiple: 
Process where two or more super class can be inherited to single sub class. It is not supported in Java since it leads to ambiguity.

#### 1.2.1.4	Hierarchical: 
Process where single super class can be inherited to two or more sub class.

### 1.2.2	Polymorphism
Polymorphism is a process where object shows different behavior at different stages of its life cycle.

##### 1.2.2.1	Compile Time Polymorphism:  
In compile time polymorphism method declaration gets binded to the method definition at compile time. Method overloading is used to achieve compile time polymorphism.

##### 1.2.2.2	Run Time Polymorphism:  
In run time polymorphism method declaration gets binded to the method definition at runtime. Method overriding is used to achieve run time polymorphism. 

###### 1.2.2.2.1	Method Overloading:  
Two or more method having same signature but different parameter is called method overloading.

###### 1.2.2.2.2	Method Overriding: 
Two or more method having same signature & same parameter is called method overriding.

### 1.2.3	Abstraction: 
Abstraction is a process of hiding class implementation and showing only class definition.

#### 1.2.3.1	Abstract class:  
Class which contains abstract method is called abstract class

##### 1.2.3.1.1	Abstract method: 
Method which contains method declaration but no definition is called Abstract method.

##### 1.2.3.1.2	Concrete method: 
Method which contain method declaration as well as method definition.

#### 1.2.3.2	Interface: 
Interface is reference type in java. It contains collection of abstract methods & is used to achieve 100% abstraction & also used to overcome multiple inheritances. Interface contains interface keyword.


### 1.2.4	Encapsulation: 
Encapsulation is a process of binding code and data in a single unit of place. Java Bean is the best example for Encapsulation.

## 1.3	Exception Handling: 

Exception is as event which trigger at runtime which will terminate the current execution flow of the program or code. Hence we go for an Exception Handling.

<b> Exception Handling:</b> is a Handler that handles the Exception so that program continues to execute even after coming across abnormal condition or a statement. It can be handled by using try catch block.

Try block is a statement which triggers the exception; Catch block is a handler that handles the exception. Each try block can have any number of catch blocks only those block which matches with the try block will be executed.

In Exception Mainly there are 2 types;
<ul>
 <li>Checked Exception </li>
 <li>Unchecked Exception</li>
</ul>

|Checked Exception	|Unchecked Exception|
|------------------|---------------------|
|Compiler detects and identifies the type of Exception which occurs at compile time.	|Here compiler will not detect & identifies the type of exception occur at compile time.|
|Is also known as compile time Exception or Caught Exception.	|Is also known as Runtime Exception or Uncaught Exception|
|All the Exception which will come under throwable class other than runtime exception is called checked Exception 	|All the exception which will come under runtime exception is called unchecked exception.|
|Ex: ClassNotFound, FileNotFound, SQLException, IOException	|Ex: ArithmeticException, ArrayIndexOutOfBoundException,NullPointerException,NumberFormatException|


<b> Note: </b>
Error: Error is irrecoverable eg: OutOfMemoryErorr, VirtualMachineError, AssertionError.

<b> Keywords of Java Exception: </b>

<ul>
 <li><b>try</b> – block is a statement which will trigger the exception. The try keyword is used to specify a block where we should place exception code. The try block should be followed by catch block or finally block. It means we can’t use try block alone.</li>
</ul> 
<ul><b>catch</b> – block is a handler that handle the exception. It must be preceded by try block which means we can’t use catch block alone. It can be followed by finally block later.</ul>
<ul><b>finally</b> – block is used to execute the important code of the program. It is executed whether exception is handled or not.</ul>
<ul><b>throw</b> – The throw is a keyword used to throw an exception.</ul>
<ul><b>throws</b> – The throws keyword is used to declare an exception. It doesn’t throw an exception. It specifies that there may occur an exception in the method. It is always used with method signature.</ul>
<ul><b>throwable</b> – is a root class of Java Exception which is available in java.lang package. It is inherited by Exception and Error.</ul>

## 1.4	Thread:

•	Thread is a light weight sub-process, smallest unit of processing. <br>
•	It is a separate path of execution. <br>
•	Threads are independent. <br>
•	It uses a shared memory area.<br> 
•	If any exception occur in one thread doesn’t affect the other thread.<br>
•	Context switching between the threads are easy.<br>

<b> Thread can be created by using 2 ways, </b>
1.	By extending Thread Class.<br>
2.	By implementing Runnable interface.

### 1.4.1	Thread Types:
#### 1.4.1.1	By extending Thread Class:

Create a class which will extend Thread class and override run method & place the logic inside the run method.


#### 1.4.1.2	By implementing Runnable interface:

Create a class which will implement runnable interface and provide implementation to the run method.


### 1.4.2	Life Cycle of Thread:

According to sun, Thread life cycle in java is divided into 4 states, those are new runnable, non-runnable & terminated. For better understanding threads are divided into 5 states.

•	New 
•	Runnable 
•	Running
•	Non Runnable (Blocked)
•	Terminated

<b>New:</b> This is the state where we create an instance of the class but before invocation of start() method.

<b>Runnable:</b> Thread is in runnable sate after invocation of start() method, but the thread scheduler has not selected it to be the running thread.

<b>Running:</b> Thread is in running state if the thread scheduler has selected it.

<b>Non runnable:</b> This is the state when thread is still alive, but currently not eligible to run.

<b>Terminated:</b> Thread is in terminated or dead state when its run() method exists. 


### 1.4.3	Multithreading:

Multithreading is a process of executing multiple threads simultaneously

Multithreading and multiprocessing is used to achieve multitasking. We will use multithread rather than multiprocess since it uses shared memory area & context switching between thread also very fast & takes less time. But processing will take more time & will not use shared memory area.

### 1.4.4	Thread Deadlock:

Deadlock can occur in a situation when a Thread is waiting for an object lock which is acquired by another thread & second thread is waiting for an object lock which is acquired by first thread. Since both the threads are waiting each other to release the lock, the condition is called Deadlock and it can be overcome by using wait & notify methods.

## 1.5	Collection Framework

Collection is a framework that provides architecture to store and manipulate the group of objects.
Whenever we want to represent a group of individual objects as a single entity then we should go for the collection.

•	Collections are grow-able in nature.
•	Both Homogeneous as well as Heterogeneous data type elements.
•	Every Collection class is implemented based on some standard data structure. Hence readymade method support is available.
•	WRT memory collections are recommended to use.
•	WRT Performance collections are not recommended to use.
•	Collection can hold only objects but not primitives.


#### Difference between Array and Collection
 
|Array	|Collection|
|------|------|
|Arrays are fixed in size.	|Collections are grow-able in nature.|
|Arrays can hold only homogeneous datatype elements |Both Homogeneous as well as Heterogeneous data type elements.|
|There is no underlying data structure for arrays hence readymade method support is not available.	|Every Collection class is implemented based on some standard data structure. Hence readymade method support is available.|
|WRT Memory arrays are not recommended to use.	|WRT memory collections are recommended to use.|
|WRT performance Arrays are recommended to use.	|WRT Performance collections are not recommended to use.|
|Array can hold both primitives and object types.	|Collection can hold only objects but not primitives.|


### Collections are divided into 3 types:
<ul>
  <li>List</li>
  <li>Que</li> 
  <li>Set</li>
 </ul>

### 1.5.1	List
•	List is a type of collection and it is grow-able in nature. It grows dynamically.
•	It allows duplicate and null object to store.
•	It preserves insertion order.
•	When we should go for a collection means, whenever we want to represent group of individual object as a single entity where duplicates are allowed and insertion order is preserved.
•	Here element can be stores and retrieved based on index, iterator, for each look.
•	List contain mainly 3 types: Array List, Vector, Linked List

#### 1.5.1.1	Array List
•	Array List is a type of List which is used to store collection or group of objects.
•	It is growable in nature it grows with the size of 2^n+1.
•	It allows duplicate as well as null objects to store.
•	It preserves insertion order.
•	It uses Dynamic array data structure to store the data.
•	Here elements can be added based on index, iterator and for each loop & can be retrieved based on for each loop.
•	Whenever we want to represent group of individual objects as a separate entity where duplicates are allowed and insertion order is preserved.
  

#### 1.5.1.2	Vector
•	Vector is a type of List which is used to store the group of individual objects.
•	It is grow able in nature. It grows with the size of 2n+1.
•	It is synchronized and thread safe.
•	It is slower in performance compared to Array List.
•	It uses dynamically resizing array data structure or dynamic array data structure.


|Array List	|Vector|
|-----------|------|
|Array List is a type of List which is grow able in nature and it grows with the size of 2^n+1	|Vector is also type of List which it is grow able in nature & grows with the size of 2*n+1|
|It is not synchronized & not thread safe |	Synchronized and Thread Safe.|
|Faster in Performance	|Slower in Performance compared to Array List|
|Array List can use Iterator for traversing	|Vector uses both Iterator and Enumeration for traversing.|
 

#### 1.5.1.3	Linked List
•	Linked List is a type of List which is used to store group of object.
•	It is a type of both List as well as Que.
•	It uses doubly linked Data structure to store the data.
•	Here elements can be added by linking object to previous objects.
•	In Linked List Manipulation is faster since if we remove elements from the list it will not shift entire cells instead it will just remove the link and add links to previous object.


|Array List	|Linked List|
|-----------|-----------|
|It is type of List and it is grow able in nature	|It is type of list as well as Que and it is also grow able in nature.|
|It used Array Data structure to store the elements. 	|It used Doubly Linked List to store the elements.|
|Here Manipulation is slower, Since shifting is required.	|Here Manipulation is faster.|
|Array List can use Iterator for traversing	|It uses both Iterator and Enumeration for traversing.|
|Here element can be accessed randomly based on index	|Here elements can be accessed sequentially.|


### 1.5.2	Queue
•	Que is a type of collection used to store group of objects.
•	It maintains the first in first out order.
•	It holds the data which are about to be processed.

#### 1.5.2.1	Priority Queue
•	Priority Que is an Implementation class of Que.
•	It holds the data which are prior to processing by their priorities.
•	It stores and retrieves the element based on priority level.
•	It does not allow null values to be stored in the queue.

#### 1.5.3	Set
•	Set is a type of collection used to store the group of objects.
•	It doesn’t allow duplicate objects to store. 
•	It allows us to store at most one null value in set.
•	It does not preserve insertion order.
•	Whenever we want to represent group of individual objects as single entity where duplicates are not allowed and insertion order is not preserved.

##### 1.5.3.1	Hash Set
•	HashSet is an implementation class of Set Interface.
•	It uses hash table for storage.
•	Hashing technique is used store the elements.
•	It contains unique items.

##### 1.5.3.2	Linked Hash Set
•	It represents Linked List implementation of Set Interface.
•	It extends HashSet class and implements Set interface.
•	It also contains unique elements.
•	It preserves insertion order and permits null elements.

##### 1.5.3.3	Sorted Set
•	Sorted Set is an alternate of Set interface.
•	Elements of Sorted Set are arranged in the ascending order.
•	Whenever we want to represent group of individual objects as a single entity where duplicates are not allowed but all the objects should be inserted according to some sorting order, then we should go for sorted set.

##### 1.5.3.4	Navigable Set
•	Navigable Set is a child interface of Sorted Set.
•	It defines several methods for Navigation purpose.

##### 1.5.3.5	Tree Set
•	Tree Set is an implementation of Set interface.
•	It uses balanced tree data structure to store the data.
•	It does not allow duplicate objects to store.
•	It stores the elements by natural ascending order.


### 1.5.4	Map

•	Map is not the child interface of Collection. It’s just a part of collection.
•	If we want to represent a group of individual objects as key value pairs then should go for Map.
•	Both key & values are objects, duplicate keys are not allowed but values can be duplicated.


