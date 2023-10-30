| feature            | feature                               |
| ------------------ | ------------------------------------- |
| 1. [Arrays](#01)   | 4. [Structures and Enumerations](#04) |
| 2. [Pointers](#02) | 5. [Streams and Files](#05)           |
| 3. [Strings](#03)  |                                       |

---

## Arrays<a id="01"></a>

1.  [Introduction](#1)
2.  [Creating and Initializing Arrays](#2)
3.  [Determining the Size of Arrays](#3)
4.  [Copying Arrays](#4)
5.  [Comparing Arrays](#5)
6.  [Passing Arrays to Functions](#6)
7.  [Understanding size_t](#7)
8.  [Unpacking Arrays](#8)
9.  [Searching Arrays](#9)
10. [Sorting Arrays](#10)
11. [Multi-dimensional Arrays](#11)

## Pointers<a id="02"></a>

12. [Introduction](#12)
13. [What is a Pointer](#13)
14. [Declaring and Using Pointers](#14)
15. [Constant Pointers](#15)
16. [Passing Pointers to Functions](#16)
17. [The Relationship Between Arrays and Pointers](#17)
18. [Pointer Arithmetic](#18)
19. [Comparing Pointers](#19)
20. [Dynamic Memory Allocation](#20)
21. [Dynamically Resizing an Array](#21)
22. [Smart Pointers](#22)
23. [Working with Unique Pointers](#23)
24. [Working with Shared Pointers](#24)

## Strings<a id="03"></a>

25. [Introduction](#25)
26. [C Strings](#26)
27. [C++ Strings](#27)
28. [Modifying Strings](#28)
29. [Searching Strings](#29)
30. [Extracting Substrings](#30)
31. [Working with Characters](#31)
32. [String_Numeric Conversion Functions](#32)
33. [Escape Sequences](#33)
34. [Raw Strings](#34)

## Structures and Enumerations<a id="04"></a>

35. [Introduction](#35)
36. [Defining Structures](#36)
37. [Initializing Structures](#37)
38. [Unpacking Structures](#38)
39. [Array of Structures](#39)
40. [Nesting Structures](#40)
41. [Comparing Structures](#41)
42. [Working with Methods](#42)
43. [Operator Overloading](#43)
44. [Structures and Functions](#44)
45. [Pointers to Structures](#45)
46. [Defining Enumerations](#46)
47. [Strongly Typed Enumerations](#47)

## Streams and Files<a id="05"></a>

48. [Introduction](#48)
49. [Understanding Streams](#49)
50. [Writing to Streams](#50)
51. [Reading from Streams](#51)
52. [Handling Input Errors](#52)
53. [File Streams](#53)
54. [Writing to Text Files](#54)
55. [Reading from Text Files](#55)
56. [Writing to Binary Files](#56)
57. [Reading from Binary Files](#57)
58. [Working with File Streams](#58)
59. [String Streams](#59)
60. [Converting Values to Strings](#60)
61. [Parsing Strings](#61)

---

## Arrays

### 1. Introduction<a id="1"></a>

### 2. Creating and Initializing Arrays<a id="2"></a>

Array- We use array to store sequence of object in the memory like sequence of number and so on.

```cpp
#include<iostream>
using namespace std;

int main(){

  // size of array
  int numbers[5];

  // how to store value in array using index
  numbers[0] = 10;
  numbers[4] = 20;

  // how to access array value using index
  cout << numbers[4];

  return 0;
}


/* output
20
*/
```

---

```cpp
#include<iostream>
using namespace std;

int main(){

  // approach 1. How to initialize array using brace initializer
  // note- The first second and third will be initialize and other will be initialize to 0
  int numbers[5] = {10, 20, 30};

  // approach 2. In case we know all the value ahead of time then we dont need to specific the size of array
  // The compiler will figure out the size of array by looking brace initialize value
  int numbersBox[] = {10, 20, 30, 40, 50, 60};

  // how to access array value using index
  cout << numbersBox[5] << endl;
  // print memory address location of array
  cout << numbersBox;

  return 0;
}


/* output
60
0x61fee4
*/

```

### 3. Determining the Size of Arrays<a id="3"></a>

How to use ranged based array

```cpp
#include<iostream>
using namespace std;

int main(){

  int numbers[] = {10, 20, 30, 40, 50, 60};

  // ranged based for loop
  for(int number : numbers){
    cout << number << endl;
  }

  return 0;
}

/* output
10
20
30
40
50
60
*/

```

```cpp
#include<iostream>
using namespace std;

int main(){

  int numbers[] = {10, 20, 30, 40, 50, 60};

  // for loop
  for(int i=0; i < size(numbers); i++){
    cout << numbers[i] << endl;
  }

  return 0;
}
```

### 4. Copying Arrays<a id="4"></a>

```cpp
#include<iostream>
using namespace std;

int main(){

  int first[] = {10, 20, 30};
  int second[size(first)];

  // using for loop to copy from first array to second array
  for(int i=0; i < size(first); i++){
    second[i] = first[i];
  }

  // print second array value
  for(int number : second){
    cout << number << endl;
  }

  return 0;

}

```

### 5. Comparing Arrays<a id="5"></a>

```cpp
#include<iostream>
using namespace std;

int main(){

  int first[] = {10, 20, 30};
  int second[] = {10, 20, 30};
  // int second[] = {10, 20, 0};

  bool areEqual = true;

  for(int i = 0; i < size(first); i++){
    if(first[i] != second[i]){
      areEqual = false;
      break;
    }
  }


  cout << boolalpha << areEqual;

  return 0;

}

```

### 6. Passing Arrays to Functions<a id="6"></a>

```cpp
#include<iostream>
using namespace std;

void printNumber(int number[], int size){
  for(int i =0; i < size; i++){
    cout << number[i];
  }
}

int main(){

  int numbers[] = {10, 20, 30};

  // passing array
  printNumber(numbers, size(numbers));

  return 0;

}

```

### 7. Understanding size_t<a id="7"></a>

size_t -
t for type, is a data type define in standard library that is use to represent the size of object

```cpp
#include<iostream>
using namespace std;

int main(){

  int numbers[] = {10, 20, 30};

  cout << sizeof(int) << endl;
  cout << sizeof(size_t) << endl;

  return 0;
}

```

### 8. Unpacking Arrays<a id="8"></a>

```cpp
#include<iostream>
using namespace std;

int main(){

  int values[3] = {10, 20, 30};

  // C++ : structured binding
  // JS : destructuring
  // python : unpacking
  auto [x, y, z] = values;

  cout << x << ", " << y << ", " << z ;

  // OLD WAY or another approach
  // int x = values[0];
  // int y = values[1];
  // int z = values[2];

  return 0;
}

```

### 9. Searching Arrays<a id="9"></a>

### 10. Sorting Arrays<a id="10"></a>

### 11. Multi-dimensional Arrays<a id="11"></a>

## Pointers

### 12. Introduction<a id="12"></a>

- what are pointer and why we use them
- Declare and use pointer
- efficiently pass data
- allocate memory dynamically
- problems with pointer
- use smart pointer in modern C++ to avoid pointer problem

### 13. What is a Pointer<a id="13"></a>

Pointer-
A pointer is a special variable that holds the address of another variable in memory

Why use pointer?

- To efficiently pass large object, pass them by reference.
- Dynamic memory allocation, resize array
- Enabling polymorphism

### 14. Declaring and Using Pointers<a id="14"></a>

" & " : address of operator

" \* " : dereferencing operator or indirection operator

### 15. Constant Pointers<a id="15"></a>

### 16. Passing Pointers to Functions<a id="16"></a>

### 17. The Relationship Between Arrays and Pointers<a id="17"></a>

### 18. Pointer Arithmetic<a id="18"></a>

### 19. Comparing Pointers<a id="19"></a>

### 20. Dynamic Memory Allocation<a id="20"></a>

### 21. Dynamically Resizing an Array<a id="21"></a>

### 22. Smart Pointers<a id="22"></a>

### 23. Working with Unique Pointers<a id="23"></a>

### 24. Working with Shared Pointers<a id="24"></a>

## Strings

### 25. Introduction<a id="25"></a>

### 26. C Strings<a id="26"></a>

### 27. C++ Strings<a id="27"></a>

### 28. Modifying Strings<a id="28"></a>

### 29. Searching Strings<a id="29"></a>

### 30. Extracting Substrings<a id="30"></a>

### 31. Working with Characters<a id="31"></a>

### 32. String_Numeric Conversion Functions<a id="32"></a>

### 33. Escape Sequences<a id="33"></a>

### 34. Raw Strings<a id="34"></a>

## Structures and Enumerations

### 35. Introduction<a id="35"></a>

### 36. Defining Structures<a id="36"></a>

### 37. Initializing Structures<a id="37"></a>

### 38. Unpacking Structures<a id="38"></a>

### 39. Array of Structures<a id="39"></a>

### 40. Nesting Structures<a id="40"></a>

### 41. Comparing Structures<a id="41"></a>

### 42. Working with Methods<a id="42"></a>

### 43. Operator Overloading<a id="43"></a>

### 44. Structures and Functions<a id="44"></a>

### 45. Pointers to Structures<a id="45"></a>

### 46. Defining Enumerations<a id="46"></a>

### 47. Strongly Typed Enumerations<a id="47"></a>

## Streams and Files

### 48. Introduction<a id="48"></a>

### 49. Understanding Streams<a id="49"></a>

### 50. Writing to Streams<a id="50"></a>

### 51. Reading from Streams<a id="51"></a>

### 52. Handling Input Errors<a id="52"></a>

### 53. File Streams<a id="53"></a>

### 54. Writing to Text Files<a id="54"></a>

### 55. Reading from Text Files<a id="55"></a>

### 56. Writing to Binary Files<a id="56"></a>

### 57. Reading from Binary Files<a id="57"></a>

### 58. Working with File Streams<a id="58"></a>

### 59. String Streams<a id="59"></a>

### 60. Converting Values to Strings<a id="60"></a>

### 61. Parsing Strings<a id="61"></a>
