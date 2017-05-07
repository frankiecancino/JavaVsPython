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
[Sources (Documentation & Code)](https://github.com/frankiecancino/JavaVsPython/blob/master/Sources.md)
