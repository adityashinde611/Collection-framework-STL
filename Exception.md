Java Exception
  An exception is an unexcepted event that occurs during program execution. It affectsbthe flow of the program instructions which can cause the program to teminate abnormally.

An exception can occur for many resons. Some of them are:
  Invalid user input 
  Device failure
  Loss of network connection
  Physical Limitations(out of disk memory)
  Code errors
  Opening an unavailable file.

Java Runtime Exceptions

A runtime exception happens due to a programming error. They are also known as unchecked exceptions.
These exceptions are not checked at compile time but run-time.Some of the common runtime exceptions are:
  Null pointer access(missing the initialization of a variable)-NullPointerException
  Out-of-bounds array access - ArrayIndexOutOfBoundsException
  Dividing a number by 0- ArithmeticException

Java IOException Exceptions

An IOException is also known as a checked exception. They are checked by the compiler at the compile-time and the programmer is prompted to handle these exceptions.
Some of the examples of checked exceptions are:
  Trying to open a file that doesn't exist result in FileNotFoundException
  Trying to read past the end of a file

try-catch block

the try..catch block in java is used to handle exceptions and prevents the abnormal termination of the program

try{
//code
}catch(exception)
{
//code
}

try-catch-finally block

In Java, we can also use the finally block after the try...catch block.
In this case, the finally vlock is always executed wether there is an exception inside the try block or not.
It is a good practice to use finally block to include important cleanup code like closing a file or connection.

NOte: There are some cases when a finallt block does not execute:
  Use of System.exit() method
  An exception occurs in the finally block
  The death of a thread

Java throw and throws
  We use the throws keyword in the method declaration to declare the type of exceptions that might occur within it
  import java.io.*;
  class Main()
  {
    public static void findFile() thows IOException{
      File newFile = new File("test.txt");
      FileInputStream stream = new FileInputStream(newFile);
    }
  }

  The throw keyword is used to explicitly throw a single exception.
  class Main{
  public static void divideByZero(){
  throw new ArithmeticException("Trying to divide by 0");
  }
  }
  Wrapper Classes 
    A wrapper class in Java is a class whose object wraps or contains primitive data types. When we create an object to a wrapper class, it contains a field and in this field, we can store primitive data types.

Need of Wrapper classes
  The classes in java.util package handles only objects and hence wrapper classes help in this case also.
  Data structures in the collection framework, such as arraylist and vector, store only objects(reference types) and not primitive types.
  An object is needed to support synchronization in multithreading.

Autoboxing & Unboxing 
  The automatic conversion of primitive types to the object of their corresponding wrapper classes is known as autoboxing. For example - conversion of int to integer, long to Long double to Double, etc.

  It is just the reverse process of autoboxing. Automatically converting an object of a wrapper class to its corresponding primitive type is known as unboxing.For example - conversion of integer to int, Long to long, Double to double, etc.

Generics 

Generics means parameterized types. Using Generics, it is possible to create classes that work with different data types. An entity such as class, interface, or method that operates on a parameterized type is a generic entity.

//create a generics class
class GenericsClass<T>
{
  private T data;
  public GenericsClass(T data)
  {
    this.data = data;
  }

  public T getData()
  {
    return this.data;
  }
}

Java Generics Method 
Similar to the generics class, we can also create a method that can be used with any type of data. Such a class is known as Generics Method.

  public <T> void genericMethod(T data) {...}

Here, the type parameter <T> is inserted after the modifier public and before the return type void.
We can call the generics method by placing the actual type <String> and <integer> inside the bracket before the method name.

  demo.<String>genericMethod("Java Programming");
  demo.<Integer>genericMethod(25);
