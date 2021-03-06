# Jigsaw Labs - Data Engineering Course

* Data Structures
* Exploring Datatypes
* Lists of Dictionaries
* List Comprehension
* Conditionals
* Filtering and Sorting
* [Functions](#functions)
* [Continuing Functions](#continuing-functions)
* [APIs and REST](#apis-and-rest)
* [APIs and Python](#apis-and-python)
* [Foursquare API](#foursquare-api)
* [Spotify API](#spotify-api)
* [Command Line](#command-line)
* [Git and GitHub](#git-and-github)
* [Introducing Testing](#introducing-testing)
* [Object Oriented Programming](#object-oriented-programming)
* [Deeper with Objects](#deeper-with-objects)
* [Object Properties](#object-properties)
* [Object Relations and ETL](#object-relations-and-etl)
* [SQL Fundamentals](#sql-fundamentals)
* [Postgres](#postrges)
* [Sampling Techniques](#sampling-techniques)
* [Postgres and Python](#postgres-and-python)



# Functions 

- Saving work with functions
- Function arguments

A **function** is a named sequence of statements that performs a computation. When you define a functionn, you specify the name and the sequence of statements. Later, you can "call" the function by name.

The name of the function is a type. The expression in parenthesis is called the **argument** of the function. It is common to say that a function "takes" an argument and "returns" a result. The result is also called the **return value**. 

A **function definition** specifies the name of a new function and the sequence of statements that run when the function is called. 

The first line of the function defintion is called the **header**; the rest is called the **body**. Defining a function creates a **function object**, a value created by a function defintion. The name of the function is a variable that refers to a function object. 

A **parameter**: A name used inside a function to refer to the value passed as an argument. 

A **traceback**: A list of the functions that are executing, printed when an exception occurs. 

``print(print_lyrics)
<function print_lyrics at 0xb7e99e9c>
``

# Continuing Functions

- Refactor functions
- Keyword arguments and default arguments

**refactoring**: The process of modifying a working program to improve functions interfaces and other qualities of the code. 


# APIs and REST

 - Instant Data
 - APIs in four lines
 - Understanding URLs
 - Exploring URLs lab
 - Developer tools with APIs
 - Requests and responses
 
We went over the Google Books API and how it works. The main takeaway was to understand how and where to start the query in a URL. It will usually start with `?.`


# APIs and Python

- Query parameters lab
- Calling APIs with Python

# Foursquare API

- Signing up for an API
- Navigating the Foursquare API
- Foursquare methods

# Spotify API

Even though this wasn't part of the lab, I did come upon a probelm that I would like highlighed. They're called nested dictionaries. View this YouTube video called [Python - Accessing Nested Dictionnary Keys](https://www.youtube.com/watch?v=oQfNYqz8pLs). It does a really good job of explaining how to access values from nested dictionaries. 

Apparently you can do a lot with the `import json` package. Check out this video [here](https://www.youtube.com/watch?v=1lxrb_ezP-g) titled "How to Write Python Scripts to Analyze JSON APIs and and if you have a lot of extra time you would watch this

# Command Line

# Git and GitHub


* [Introducing Testing](#introducing-testing)
* [Object Oriented Programming](#object-oriented-programming)
* [Deeper with Objects](#deeper-with-objects)
* [Object Properties](#object-properties)
* [Object Relations and ETL](#object-relations-and-etl)
* [SQL Fundamentals](#sql-fundamentals)
* [Postgres](#postrges)
* [Sampling Techniques](#sampling-techniques)

# Postgres and Python

Mass assignment - we need to first learn: `setattr` (set attribute) method and how to access keyword arguments in Python. 

`setattr()` function sets the value of the attribute of an object. 

`setattr(object, name, value)`

    class Person:
     name='Susan'

    p = Person()
    print('Before modification:', p.name)

    # setting name to 'John'
    setattr(p, 'name', 'John')

    print('After modification:', p.name)
    
You can even set an attribute when it is not present in Person

    setattr(p, 'age', 23)
    print('Age is:', p.age)

You can check all the attributes of an object by using the `dir()` function. 

One more thing to learn to set up mass assignment: kwargs

`**kwargs` tells us we can pass through as many keyword arguments as wel like when creating a new class, in our example above we used Person. 

    class User():
     def __init__(self, **kwargs):
      for key, value in kwargs.items():
        setattr(self, key, value)

    user = User(name='fred, birthday='8/3/2020')

`kwargs.items()` will get you `kwargs = {'name':'fred', 'birthday':'8/3/2020'}`

Because in script above can pass through any atribute, we need to raise an error for unwanted attributes. Let's rewrite the code from above: 

    class User():
      __table__ = 'users'

      columns = ['id','name','birthday']
      def __init__(self, **kwargs):
        for key in kwargs.keys()
          if key not in self.columns:
             raise ValueError(f'{key} not in columns: {self.columns}')
          for k, v in kwargs.items():
            setattr(self, k, v)

mass assignment in our classes -> **kwargs & setattr() function. 


