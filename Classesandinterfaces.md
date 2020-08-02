https://www.typescriptlang.org/docs/handbook/interfaces.html#:~:text=Interfaces%20are%20capable%20of%20describing,the%20interface%20a%20call%20signature.

Differences between Abstract Classes and Interface
An interface contains a set of methods that haven’t been implemented. A class that references the interface must override these methods. This allows the class to be a part of two classes at one time (multiple-inheritance) – once as a normal sub-class and once as a “sub-class” of an interface.

An abstract class, like an interface, will contain methods. However, there always will be at least one method that hasn’t been completed. This is one major difference between an abstract class and an interface. The abstract class will provide a guideline (a base class definition) from which derived classes will begin. You, the programmer, will be able to implement these derived classes. You can only define abstract methods in abstract classes. However, it’s not necessary that you define an abstract method when you define an abstract class.

Apart from this major difference, here are some other differences between the two:

A class can only inherit from one abstract class at a time. However, a class may inherit from multiple interfaces. Interfaces are used to implement the concept of multiple inheritance in object oriented programming.

Because an abstract class is a real class, it can have access modifiers for its functions and properties, like for regular classes. Because an interface is not a class, it does not allow access modifiers.  Everything is considered public (open to everything) by default.

An interface is just an empty signature and does not contain a body (code). An abstract class can provide code, i.e., methods that have to be overridden.

Abstract classes are used when we require classes to share a similar behavior (or methods). However, if we need classes to share method signatures, and not the methods themselves, we should use interfaces.

We could say that an abstract class is processed faster by the pc, but it depends on the code we have written. Sometimes an interface is faster (because it’s just a bunch of empty names). Sometimes an abstract class is processed faster, as the pc doesn’t need to refer to derived class for a method.

It takes more time to add new methods to an interface. Code has to be rewritten for the interface and for all classes that refer to it include the new methods. It’s easier to add code to an abstract class, because we can use it as the default implementation. The program will still continue to run properly.

Because an interface is empty, it cannot have constants or fields. An abstract class can contain fields and constants definitions.

Interfaces can add to the existing functionality of a class. They are not necessarily integral to the identity of the classes that reference them. Abstract classes, on the other hand, provide an identity to the classes that derive from them, as they inherit their behaviors from it.

Summing up, we can say that the major difference between an abstract class and an interface is the methods they contain (completed versus uncompleted) and their contents (a real class vs. an empty template). If you’re unsure whether to use an abstract class or an interface, make sure you better understand advanced Java programming concepts to make a more informed choice.interface 
