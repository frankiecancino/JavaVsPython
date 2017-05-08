# Java vs Python
Description of the similarities and differences between the programming languages of Java and Python

Authors: Frankie Cancino & Daniel Hanson

## Java
* Language purpose/genesis
  * Why was the language created?
  * What problems was the language trying to address?
  * Is the language a reaction to a previous language or a replacement for another language?
* Unique features of the language
  * Does the language have any particularly unique features?
* Name spaces
  * How are name spaces implemented?
  * How are name spaces used?
* Types
    * What types does the language support?
    * Are both reference and value types supported?
    * Can new value types be created?
* Classes
  * Defining
  * Creating new instances
  * Constructing/initializing
  * Destructing/de-initializing
* Instance reference name in data type (class)
  * this?  self?
* Properties
  * Getters and setters...write your own or built in?
  * Backing variables?
  * Computed properties?
* Interfaces / protocols
  * What does the language support?
  * What abilities does it have?
  * How is it used?
* Inheritance / extension
* Reflection
  * What reflection abilities are supported?
  * How is reflection used?
* Memory management
  * How is it handled?
  * How does it work?
  * Garbage collection?
  * Automatic reference counting?
* Comparisons of references and values
  * How are values compared? (i.e. comparing two strings)
* Null/nil references
  * Which does the language use? (null/nil/etc)
  * Does the language have features for handling null/nil references?
* Errors and exception handling
* Lambda expressions, closures, or functions as types
* Implementation of listeners and event handlers
* Singleton
  * How is a singleton implemented?
  * Can it be made thread-safe?
  * Can the singleton instance be lazily instantiated?
* Procedural programming
  * Does the language support procedural programming?
* Functional programming
  * Does the language support functional programming?
* Multithreading
  * Threads or thread-like abilities
  * How is multitasking accomplished?

---
[Java Sources (Documentation & Code)](https://github.com/frankiecancino/JavaVsPython/blob/master/JavaSources.md)

## Python
* Language purpose/genesis
  * Why was the language created?
    * We needed a better way to do system administration than by writing either C programs or Bourne shell scripts, a scripting language with a syntax like ABC but with access to the Amoeba system calls would fill the need. Python was used in the Amoeba project with increasing success.
  * What problems was the language trying to address?
    * The language comes with a large standard library that covers areas such as string processing (regular expressions, Unicode, calculating differences between files), Internet protocols (HTTP, FTP, SMTP, XML-RPC, POP, IMAP, CGI programming), software engineering (unit testing, logging, profiling, parsing Python code), and operating system interfaces (system calls, filesystems, TCP/IP sockets).
  * Is the language a reaction to a previous language or a replacement for another language?
    * C programs or Bourne shell scripts
* Unique features of the language
  * Does the language have any particularly unique features?
    * Uses an elegant syntax, making the programs you write easier to read. Is an easy-to-use language that makes it simple to get your program working. This makes Python ideal for prototype development and other ad-hoc programming tasks, without compromising maintainability. Comes with a large standard library that supports many common programming tasks such as connecting to web servers, searching text with regular expressions, reading and modifying files. Python's interactive mode makes it easy to test short snippets of code. Is easily extended by adding new modules implemented in a compiled language such as C or C++. Can also be embedded into an application to provide a programmable interface. Runs anywhere, including Mac OS X, Windows, Linux, and Unix. Is free software in two senses. It doesn't cost anything to download or use Python, or to include it in your application. Python can also be freely modified and re-distributed, because while the language is copyrighted it's available under an open source license.
* Name spaces
  * How are name spaces implemented?
    * Namespaces are created at different moments and have different lifetimes. The namespace containing the built-in names is created when the Python interpreter starts up, and is never deleted. The global namespace for a module is created when the module definition is read in; normally, module namespaces also last until the interpreter quits. The statements executed by the top-level invocation of the interpreter, either read from a script file or interactively, are considered part of a module called __main__, so they have their own global namespace. (The built-in names actually also live in a module; this is called builtins.) The local namespace for a function is created when the function is called, and deleted when the function returns or raises an exception that is not handled within the function. (Actually, forgetting would be a better way to describe what actually happens.) Of course, recursive invocations each have their own local namespace.
    ```
    def scope_test():
    def do_local():
        spam = "local spam"

    def do_nonlocal():
        nonlocal spam
        spam = "nonlocal spam"

    def do_global():
        global spam
        spam = "global spam"

    spam = "test spam"
    do_local()
    print("After local assignment:", spam)
    do_nonlocal()
    print("After nonlocal assignment:", spam)
    do_global()
    print("After global assignment:", spam)

    scope_test()
    print("In global scope:", spam)
    ```
  * How are name spaces used?
    * Most namespaces are currently implemented as Python dictionaries, but that’s normally not noticeable in any way (except for performance), and it may change in the future. Examples of namespaces are: the set of built-in names (containing functions such as abs(), and built-in exception names); the global names in a module; and the local names in a function invocation. In a sense the set of attributes of an object also form a namespace. The important thing to know about namespaces is that there is absolutely no relation between names in different namespaces; for instance, two different modules may both define a function maximize without confusion — users of the modules must prefix it with the module name.
* Types
    * What types does the language support?
      * boolean: the type of the built-in values True and False. Useful in conditional expressions, and anywhere else you want to represent the truth or falsity of some condition. Mostly interchangeable with the integers 1 and 0. In fact, conditional expressions will accept values of any type, treating special ones like boolean False, integer 0 and the empty string "" as equivalent to False, and all other values as equivalent to True. But for safety’s sake, it is best to only use boolean values in these places.
      * Numeric types:

        * int: Integers; equivalent to C longs in Python 2.x, non-limited length in Python 3.x
        * long: Long integers of non-limited length; exists only in Python 2.x
        * float: Floating-Point numbers, equivalent to C doubles
        * complex: Complex Numbers
      * Sequences:

        * str: String; represented as a sequence of 8-bit characters in Python 2.x, but as a sequence of Unicode characters (in the range of U+0000 - U+10FFFF) in Python 3.x
        * bytes: a sequence of integers in the range of 0-255; only available in Python 3.x
        * byte array: like bytes, but mutable (see below); only available in Python 3.x
        * list
        * tuple
      * Sets:

        * set: an unordered collection of unique objects; available as a standard type since Python 2.6
        * frozen set: like set, but immutable (see below); available as a standard type since Python 2.6
      * Mappings:

        * dict: Python dictionaries, also called hashmaps or associative arrays, which means that an element of the list is associated with a definition, rather like a Map in Java
    * Are both reference and value types supported?
      * The authors who call the mechanism call-by-value and those who call it call-by-reference are stretching the definitions until they fit. Correctly speaking, Python uses a mechanism, which is known as "Call-by-Object", sometimes also called "Call by Object Reference" or "Call by Sharing". If you pass immutable arguments like integers, strings or tuples to a function, the passing acts like call-by-value. The object reference is passed to the function parameters. They can't be changed within the function, because they can't be changed at all, i.e. they are immutable. It's different, if we pass mutable arguments. They are also passed by object reference, but they can be changed in place in the function. If we pass a list to a function, we have to consider two cases: Elements of a list can be changed in place, i.e. the list will be changed even in the caller's scope. If a new list is assigned to the name, the old list will not be affected, i.e. the list in the caller's scope will remain untouched. 
    * Can new value types be created?
      * Python allows the writer of an extension module to define new types that can be manipulated from Python code, much like strings and lists in core Python.
* Classes
  * Defining
    ```
    class ClassName:
    <statement-1>
    .
    .
    .
    <statement-N>
    ```
  * Creating new instances
    * Data attributes correspond to “instance variables” in Smalltalk, and to “data members” in C++. Data attributes need not be declared; like local variables, they spring into existence when they are first assigned to. For example, if x is the instance of MyClass created above, the following piece of code will print the value 16, without leaving a trace:
    ```
    x.counter = 1
    while x.counter < 10:
     x.counter = x.counter * 2
    print(x.counter)
    del x.counter
    ```
  * Constructing/initializing
    ```
    class Dog:

    def __init__(self, name):
        self.name = name
        self.tricks = []    # creates a new empty list for each dog

    def add_trick(self, trick):
        self.tricks.append(trick)

    d = Dog('Fido')
    d.add_trick('roll over')
    d.tricks ['roll over']
    ```
  * Destructing/de-initializing
    ```
    x.counter = 1
    while x.counter < 10:
     x.counter = x.counter * 2
    print(x.counter)
    del x.counter
    ```
* Instance reference name in data type (class)
  * this?  self?
    * Often, the first argument of a method is called self. This is nothing more than a convention: the name self has absolutely no special meaning to Python. Note, however, that by not following the convention your code may be less readable to other Python programmers, and it is also conceivable that a class browser program might be written that relies upon such a convention.
* Properties
  * Getters and setters...write your own or built in?
    * Python is not Java. If you need to set or get the members of a class or object, just expose the member publicly and access it directly. If you need to perform some computations before getting or setting the member, then use Python’s built-in property decorator.
  * Backing variables?
    * Properties is a way of defining the methods of setting, getting and deleting attributes of a function. They let you use methods to define how the field should be accessed and then allow you to use the standard interface for fields.
  * Computed properties?
    ```
    class Widget(object):
    def __init__(self, arg=None):
        if arg:
            self.color_data = arg
        else:
            self.color_data = (0,0,0)

    def get_color(self):
        if type(self.color_data) is tuple:
            return self.color_data
        else:
            return str_to_tuple(self.color_data)

    def set_color(self, arg):
        self.color_data = arg

    # create property object to dispatch 'get' and 'set' methods
    # NOTE: "color" is a class attribute, not an instance attribute
    color = property(get_color, set_color)
    ```
* Interfaces / protocols
  * What does the language support?
    * Python, interfaces are much more dynamic than their counterparts in Java.
  * What abilities does it have?
    * Java doesn't let you change your mind on the fly about what interface a class or an instance supports, but Python does. Java requires you to write your interface in the form of a class, while in Python you can use a class, an object, generate it on the fly, pretty much whatever you want.
  * How is it used?
    * If you're creating a framework, the situation is different. A framework is a library that calls the framework user's code. Now, somebody will be writing code that -- in effect -- is part of your library, and they need to know things about how their code will be called. With a library, it's okay if the author or maintainers are the only ones who know the internal dependencies of their code. But with a framework, the users are effectively co-authors and co-maintainers. They need more concrete information.
    ```
    class IIterable(Interface):
     def __iter__():

    class IIterator(IIterable):
     def next():
    ```
* Inheritance / extension
 * Python has two built-in functions that work with inheritance:
  * Use isinstance() to check an instance’s type: isinstance(obj, int) will be True only if obj.__class__ is int or some class derived from int.
  * Use issubclass() to check class inheritance: issubclass(bool, int) is True since bool is a subclass of int. However, issubclass(unicode, str) is False since unicode is not a subclass of str (they only share a common ancestor, basestring).
* Reflection
  * What reflection abilities are supported?
  
  * How is reflection used?
  
* Memory management
  * How is it handled?
  
  * How does it work?
  
  * Garbage collection?
  
  * Automatic reference counting?
  
* Comparisons of references and values
  * How are values compared? (i.e. comparing two strings)
  
* Null/nil references
  * Which does the language use? (null/nil/etc)
  
  * Does the language have features for handling null/nil references?
  
* Errors and exception handling

* Lambda expressions, closures, or functions as types

* Implementation of listeners and event handlers

* Singleton
  * How is a singleton implemented?
  
  * Can it be made thread-safe?
  
  * Can the singleton instance be lazily instantiated?
  
* Procedural programming
  * Does the language support procedural programming?
  
* Functional programming
  * Does the language support functional programming?
  
* Multithreading
  * Threads or thread-like abilities
  
  * How is multitasking accomplished?

---
[Python Sources (Documentation & Code)](https://github.com/frankiecancino/JavaVsPython/blob/master/PythonSources.md)
