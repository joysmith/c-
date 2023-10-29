| feature                                | feature              |
| -------------------------------------- | -------------------- |
| 1. [Classes](#01)                      | 4. [Exceptions](#04) |
| 2. [Operator Overloading](#02)         | 5. [Templates](#05)  |
| 3. [Inheritance and Polymorphism](#03) |                      |

## Classes<a id="01"></a>

1.  [Introduction](#1)
2.  [An Introduction to Object-oriented Programming](#2)
3.  [Defining a Class](#3)
4.  [Creating Objects](#4)
5.  [Access Modifiers](#5)
6.  [Getters and Setters](#6)
7.  [Constructors](#7)
8.  [Member Initializer List](#8)
9.  [The Default Constructor](#9)
10. [Using the Explicit Keyword](#10)
11. [Constructor Delegation](#11)
12. [The Copy Constructor](#12)
13. [The Destructor](#13)
14. [Static Members](#14)
15. [Constant Objects and Functions](#15)
16. [Pointer to Objects](#16)
17. [Array of Objects](#17)

## Operator Overloading<a id="02"></a>

18. [Introduction](#18)
19. [Overloading the Equality Operator](#19)
20. [Overloading the Comparison Operators](#20)
21. [Overloading the Spaceship Operator](#21)
22. [Overloading the Stream Insertion Operator](#22)
23. [Overloading the Stream Extraction Operator](#23)
24. [Friends of Classes](#24)
25. [Overloading the Arithmetic Operators](#25)
26. [Overloading Compound Assignment Operators](#26)
27. [Overloading the Assignment Operator](#27)
28. [Overloading Unary Operators](#28)
29. [Overloading the Subscript Operator](#29)
30. [Overloading the Indirection Operator](#30)
31. [Overloading Type Conversions](#31)
32. [Inline Functions](#32)

## Inheritance and Polymorphism<a id="03"></a>

33. [Introduction](#33)
34. [Inheritance](#34)
35. [Protected Members](#35)
36. [Constructors and Inheritance](#36)
37. [Destructors and Inheritance](#37)
38. [Conversion between Base and Derived Classes](#38)
39. [Overriding Methods](#39)
40. [Polymorphism](#40)
41. [Polymorphic Collections](#41)
42. [Virtual Destructors](#42)
43. [Abstract Classes](#43)
44. [Final Classes and Methods](#44)
45. [Deep Inheritance Hierarchies](#45)
46. [Multiple Inheritance](#46)

## Exceptions<a id="04"></a>

47. [Introduction](#47)
48. [What are Exceptions](#48)
49. [Throwing an Exception](#49)
50. [Catching an Exception](#50)
51. [Catching Multiple Exceptions](#51)
52. [Where to Catch Exceptions](#52)
53. [Rethrowing an Exception](#53)
54. [Creating Custom Exceptions](#54)

## Templates<a id="05"></a>

55. [Introduction](#55)
56. [Defining a Function Template](#56)
57. [Explicit Type Arguments](#57)
58. [Templates with Multiple Parameters](#58)
59. [Defining a Class Template](#59)
60. [A More Complex Class Template](#60)

---

## Classes

### 1. Introduction<a id="1"></a>

### 2. An Introduction to Object-oriented Programming<a id="2"></a>

Programming paradigm or style of programming

Programming paradigm

1. Procedural
1. Functional (popular)
1. Object oriented (popular)
1. event driven

| Functional            | Object oriented    |
| --------------------- | ------------------ |
| Centered on functions | Centered on object |
| C                     | C++                |

Which one to use?
A wise software engineer uses the right tools for the right job.
depend on your requirement

---

Object:

- A software entity that has attributes(properties) and functions(methods)

<br>

> **Dialog box**

<img src="notes/dialog.png" width="400">

Attributes

- size
- position on screen

Functions

- show()
- hide()
- resize()
- move()
- maximize()
- minimize()

---

> **Video player**

<img src="notes/vlc.png" width="400">

Attributes

- size
- currentPosition
- playbackSpeed

Functions

- play()
- pause()
- stop()

---

Class:
<br>

<img src="notes/uml.png" width="400">

- A blueprint or recipe for creating objects
- With class we are defining new data type, we can also do that with structure

| Structure                                     | Classes                                              |
| --------------------------------------------- | ---------------------------------------------------- |
| Data                                          | Data + Behavior                                      |
| The structure are simple data container       | Classes for creating object that can do things       |
| structure are more about data                 | Classes are more about data & functionality together |
| Structure member are always public by default | Classes member are always private by default         |

---

Encapsulation:
Combining the data and functions that operate on the data into one unit.

<br>

<img src="notes/membervariable.png" width="400">

<br>

<img src="notes/membermethod.png" width="400">

### 3. Defining a Class<a id="3"></a>

### 4. Creating Objects<a id="4"></a>

### 5. Access Modifiers<a id="5"></a>

### 6. Getters and Setters<a id="6"></a>

### 7. Constructors<a id="7"></a>

### 8. Member Initializer List<a id="8"></a>

### 9. The Default Constructor<a id="9"></a>

### 10. Using the Explicit Keyword<a id="10"></a>

### 11. Constructor Delegation<a id="11"></a>

### 12. The Copy Constructor<a id="12"></a>

### 13. The Destructor<a id="13"></a>

### 14. Static Members<a id="14"></a>

### 15. Constant Objects and Functions<a id="15"></a>

### 16. Pointer to Objects<a id="16"></a>

### 17. Array of Objects<a id="17"></a>

## Operator Overloading

### 18. Introduction<a id="18"></a>

### 19. Overloading the Equality Operator<a id="19"></a>

### 20. Overloading the Comparison Operators<a id="20"></a>

### 21. Overloading the Spaceship Operator<a id="21"></a>

### 22. Overloading the Stream Insertion Operator<a id="22"></a>

### 23. Overloading the Stream Extraction Operator<a id="23"></a>

### 24. Friends of Classes<a id="24"></a>

### 25. Overloading the Arithmetic Operators<a id="25"></a>

### 26. Overloading Compound Assignment Operators<a id="26"></a>

### 27. Overloading the Assignment Operator<a id="27"></a>

### 28. Overloading Unary Operators<a id="28"></a>

### 29. Overloading the Subscript Operator<a id="29"></a>

### 30. Overloading the Indirection Operator<a id="30"></a>

### 31. Overloading Type Conversions<a id="31"></a>

### 32. Inline Functions<a id="32"></a>

## Inheritance and Polymorphism

### 33. Introduction<a id="33"></a>

### 34. Inheritance<a id="34"></a>

### 35. Protected Members<a id="35"></a>

### 36. Constructors and Inheritance<a id="36"></a>

### 37. Destructors and Inheritance<a id="37"></a>

### 38. Conversion between Base and Derived Classes<a id="38"></a>

### 39. Overriding Methods<a id="39"></a>

### 40. Polymorphism<a id="40"></a>

### 41. Polymorphic Collections<a id="41"></a>

### 42. Virtual Destructors<a id="42"></a>

### 43. Abstract Classes<a id="43"></a>

### 44. Final Classes and Methods<a id="44"></a>

### 45. Deep Inheritance Hierarchies<a id="45"></a>

### 46. Multiple Inheritance<a id="46"></a>

## Exceptions

### 47. Introduction<a id="47"></a>

### 48. What are Exceptions<a id="48"></a>

### 49. Throwing an Exception<a id="49"></a>

### 50. Catching an Exception<a id="50"></a>

### 51. Catching Multiple Exceptions<a id="51"></a>

### 52. Where to Catch Exceptions<a id="52"></a>

### 53. Rethrowing an Exception<a id="53"></a>

### 54. Creating Custom Exceptions<a id="54"></a>

## Templates

### 55. Introduction<a id="55"></a>

### 56. Defining a Function Template<a id="56"></a>

### 57. Explicit Type Arguments<a id="57"></a>

### 58. Templates with Multiple Parameters<a id="58"></a>

### 59. Defining a Class Template<a id="59"></a>

### 60. A More Complex Class Template<a id="60"></a>
