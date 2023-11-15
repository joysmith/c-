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

<img src="notes//address.png" width="400">

" & " : address of operator

" \* " : dereferencing operator or indirection operator

```cpp
#include<iostream>
using namespace std;

int main(){

  // every variable has an address
  int number = 10;

  // how to print memory address of number variable using '&'
  cout << &number;

  // how to initialize null pointer
  // int* ptr = nullptr;

  // how to declare integer pointer
  int* ptr = &number;

  // how to access data at target memory location
  cout << *ptr << endl;

  // how to change data at target memory location
  *ptr = 20;

  cout << number;

  return 0;
}



/* output
0x61ff0810
20
*/
```

---

```cpp
#include<iostream>
using namespace std;

int main(){

  int x = 10;
  int y = 20;

  int* ptr = &x;  // pointing to x

  *ptr *= 2;  // x = 20

  ptr = &y; // set address to y

  *ptr *= 3;  // y = 60

  return 0;
}

```

---

Way to declare pointer, notice place of \*

```cpp

int number = 10;

✅ preferable
int* ptr = &number;

// confusing with dereference operator
int *ptr = &number;
```

### 15. Constant Pointers<a id="15"></a>

Pointe & constant: 3 scenario

- data is constant but pointer is not, so later we can use pointer to point something else
- pointer is constant, so once we declare and initialize the pointer we cannot have it point to something else
- both data and pointer are constant

---

Scene 1: data is constant but pointer is not

```cpp

#include<iostream>
using namespace std;

int main(){

  const int x = 10;

  // constant integer pointer, but pointer is not constant
  const int* ptr = &x;

  int y = 20;

  ptr = &y;

  return 0;
}

```

---

Scene 2: pointer is constant

```cpp
#include<iostream>
using namespace std;

int main(){

  int x = 10;

  // pointer is constant
  int* const ptr = &x;

  return 0;
}

```

---

Scene 3: both data and pointer are constant

```cpp
#include<iostream>
using namespace std;

int main(){

  const int x = 10;

  // How to read the line: we have constant pointer, pointing to constant integer
  const int* const ptr = &x;

  return 0;
}

```

### 16. Passing Pointers to Functions<a id="16"></a>

Pass by value

```cpp
#include <iostream>
using namespace std;

void increasePrice(double price){
    price *= 1.2;
}

int main(){
    double price = 100;

    // pass by value: we pass the copy of variable price
    increasePrice(price);
    cout << price;
    return 0;
}

/* output
100
*/
```

---

1. approach/pattern: new way

```cpp
#include <iostream>
using namespace std;

void increasePrice(double& price){
    price *= 1.2;
}

int main(){
    double price = 100;

    // pass by reference: we pass the reference of variable price,
    // now we can directly access price variable through our function
    increasePrice(price);
    cout << price;
    return 0;
}


/* output
120
*/
```

---

2 approach/pattern: old way

```cpp
#include <iostream>
using namespace std;

// 1.declare parameter as pointer
void increasePrice(double* price){
    //2. indirection operator
    *price *= 1.2;
}

int main(){
    double price = 100;

    //3. address of operator to ask the address of price variable
    increasePrice(&price);
    cout << price;
    return 0;
}

/* output
120
*/
```

### 17. The Relationship Between Arrays and Pointers<a id="17"></a>

```cpp
#include <iostream>
using namespace std;

void printNumbers(int numbers[]){
    numbers[0] = 0;
}

int main(){
    int numbers[] = {10,20,30};
    printNumbers(numbers);
    cout << numbers[0];

    return 0;
}

/* output
0
*/
```

### 18. Pointer Arithmetic<a id="18"></a>

We can only perform two operation on pointer i.e addition and subtraction
NOT multiplication and division

pointer increment

```cpp
#include <iostream>
using namespace std;

int main(){
    int numbers[] = {10,20,30};
    int* ptr = numbers;

    ptr++;
    cout << *ptr;
    return 0;
}


/* output
20
*/
```

---

pointer decrement

```cpp
#include <iostream>
using namespace std;

int main(){
    int numbers[] = {10,20,30};
    int* ptr = numbers;

    ptr--;
    cout << *ptr;
    return 0;
}


/* output
10
*/
```

---

Pointer expression

```cpp
#include <iostream>
using namespace std;

int main(){
    int numbers[] = {10,20,30};
    int* ptr = numbers;
    // dereference the pointer, means access value(increment pointer by one)
    cout << *(ptr + 1);

    // same as above line but using bracket notation
    // cout << ptr[1];
    // cout << numbers[1];
    return 0;
}


/* output
20
*/
```

### 19. Comparing Pointers<a id="19"></a>

```cpp
#include <iostream>
using namespace std;

int main(){
    int x = 20;
    int y = 20;

    int* ptrX = &x;
    int* ptrY = &y;

    // comparing address
    // if(ptrX == ptrY)

    // comparing value
    if(*ptrX == *ptrY)
        cout << "same";

    return 0;
}
```

### 20. Dynamic Memory Allocation<a id="20"></a>

If we declare an array of integer like "int numbers[10];", we are limiting our program to handle maximum of 10 numbers.

Or we can allocate memory to our program at run time on demand this is called dynamic memory allocation

Stack memory:

- variable declared on stack they get automatic clean up.
- once they got out of scope the memory allocated to them, get released automatically.
-

Heap or free store memory:

- to allocate memory dynamically we use "new" operator/keyword.
- variable declared on heap using "new" operator/keyword, we programmers are responsible for the clean up.
- when we do not release memory from heap, program consume more and more memory eventually our program gonna crash this is called memory leak.
- memory leak: means our program consume more and more memory.
- to de-allocate we use "delete" operator/keyword

---

Allocating array on heap

```cpp
#include <iostream>
using namespace std;

int main(){
    // Stack memory
    // int numbers[1000];


    // Heap memory(free store)
    // allocating array on heap
    int* numbers = new int[10];

    //de allocating array memory from heap
    delete[] numbers;

    // convention: reset pointer
    numbers = nullptr;

    return 0;
}
```

---

Allocating single integer on heap

```cpp
#include <iostream>
using namespace std;

int main(){


    // Stack memory
    // int numbers[1000];

    // Heap memory(free store)
    // allocating single integer on heap
    int* number = new int;

    // de allocating single integer from memory
    delete[] number;

    // convention: reset pointer
    number = nullptr;

    return 0;
}
```

### 21. Dynamically Resizing an Array<a id="21"></a>

```cpp
#include <iostream>
using namespace std;

int main(){

// declaring integer array on heap
int* numbers = new int[5];

// declaring variable on stack
int entries =0;

while(true){
    cout << "Number: ";
    cin >> numbers[entries];

    if(cin.fail()) break;
    entries++;

}

for(int i=0; i<entries; i++)
    cout << numbers[i] << endl;

return 0;
}


/* output
 Number:1
 Number:2
 Number:3
 Number:4
 Number:5
 Number:k
 1
 2
 3
 4
 5
*/
```

---

```cpp
#include <iostream>
using namespace std;

int main(){

// declaring integer array on heap
int* numbers = new int[5];

// declaring variable on stack
int entries =0;

while(true){
    cout << "Number: ";
    cin >> numbers[entries];

    if(cin.fail()) break;
    entries++;

    if(entries ==5){
        // Algorithm for dynamic array
        // 1. create a temp array (twice the size)
        int* temp = new int[10];
        // 2. copy all the elements
        for (int i=0; i<entries; i++)
            temp[i] = numbers[i];

        // delete initial array from heap to avoid memory leak
        delete[] numbers;
        // 3. Have "numbers" pointer point to the new array
        numbers = temp;

    }
}

for(int i=0; i<entries; i++)
    cout << numbers[i] << endl;

return 0;
}

/* output
 Number:1
 Number:2
 Number:3
 Number:4
 Number:5
 Number:6
 Number:7
 Number:8
 Number:9
 Number:10
 Number:j
1
2
3
4
5
6
7
8
9
10

*/
```

---

```cpp
#include <iostream>
using namespace std;

int main(){
// declaring variable on stack
    int capacity = 5;
    int entries =0;

// declaring integer array on heap
int* numbers = new int[capacity];



while(true){
    cout << "Number: ";
    cin >> numbers[entries];

    if(cin.fail()) break;
    entries++;

    if(entries == capacity){
        // Algorithm for dynamic array
        capacity *= 2;

        // 1. create a temp array (twice the size)
        int* temp = new int[capacity];
        // 2. copy all the elements
        for (int i=0; i<entries; i++)
            temp[i] = numbers[i];

        // delete initial array from heap to avoid memory leak
        delete[] numbers;
        // 3. Have "numbers" pointer point to the new array
        numbers = temp;

    }
}

for(int i=0; i<entries; i++)
    cout << numbers[i] << endl;

delete[] numbers;

return 0;
}


/* output
 Number:1
 Number:2
 Number:3
 Number:4
 Number:5
 Number:6
 Number:7
 Number:8
 Number:9
 Number:10
 Number:11
 Number:12
 Number:13
 Number:14
 Number:15
 Number:16
 Number:17
 Number:p
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
*/
```

### 22. Smart Pointers<a id="22"></a>

There are 2 types of smart pointer

- unique pointer
- shared pointer

### 23. Working with Unique Pointers<a id="23"></a>

<img src="notes/unique.png" width="400">

Unique pointer- is a kind of pointer that owns the piece of memory it points to, we cannot have two unique pointer, pointing to the same memory location

```cpp
#include <iostream>
#include <memory>

using namespace std;

int main(){
    unique_ptr<int> xyzobj(new int);
    cout << xyzobj;

return 0;
}


/* output
0x1fc91371ad0
*/
```

---

```cpp
#include <iostream>
#include <memory>

using namespace std;

int main(){
    unique_ptr<int> xyzobj(new int);

    // dereference and store some value
    *xyzobj = 10;
    cout << *xyzobj;

return 0;
}


/* output
10
*/
```

---

```cpp
#include <iostream>
#include <memory>

using namespace std;

int main(){
    // 1 approach to create unique pointer
    unique_ptr<int> xyzobj(new int);

    // 2 approach to create unique pointer
    unique_ptr<int> y = make_unique<int>();

    // 3 approach to create unique pointer
    auto z = make_unique<int>();


    // dereference and store some value
    *xyzobj = 10;
    cout << *xyzobj;

return 0;
}
```

---

```cpp
#include <iostream>
#include <memory>

using namespace std;

int main(){

    auto numbers = make_unique<int[]>(10);
    unique_ptr<int> y = make_unique<int>();

    numbers[0] = 10;
    cout << numbers[0];

return 0;
}

/* output
10
*/
```

### 24. Working with Shared Pointers<a id="24"></a>

with shared pointer we can have 2 pointer, pointing to same memory location

<img src="notes/shared.png" width="400">

```cpp
#include <iostream>
#include <memory>

using namespace std;

int main(){

    // 1 approach: create shared pointer
    shared_ptr<int> x(new int);

    // 2 approach: create shared pointer
    shared_ptr<int> y = make_shared<int>();

    // 3 approach: create shared pointer
    auto z = make_shared<int>();


return 0;
}
```

---

```cpp
#include <iostream>
#include <memory>

using namespace std;

int main(){

    auto x = make_shared<int>();

    // dereference and store value
    *x = 10;

    shared_ptr<int> y(x);

    if(x == y)
        cout << "equal";

return 0;
}
```

---

```cpp
#include <iostream>
#include <memory>

using namespace std;

int main(){

    auto x = make_shared<int>();

    // dereference and store value
    *x = 10;

    shared_ptr<int> y(x);


    cout << *y;

return 0;
}
```

## Strings

### 25. Introduction<a id="25"></a>

- C strings
- C++ strings
- Modifying strings
- Searching strings
- Extracting substring
- Converting strings to numbers and vice versa

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
