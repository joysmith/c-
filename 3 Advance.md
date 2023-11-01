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

<br>

Object:

- A software entity that has attributes(properties) and functions(methods)

<br>

##### **Dialog box**

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

<br>

##### **Video player**

<img src="notes/vlc.png" width="400">

Attributes

- size
- currentPosition
- playbackSpeed

Functions

- play()
- pause()
- stop()

<br>

##### Other examples

- storing and retrieving data
- sending email and notifications
- Performing computations

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

- create a new file name it "Rectangle.h" for class declaration

```cpp
class Rectangle{
  public:
  // member variable
  int width;
  int height;

  // member function
  void draw();
  int getArea();
};
```

---

- create a new file name it "Rectangle.cpp" for class definition/implementation

```cpp
#include<iostream>
#include "Rectangle.h"

using namespace std;

void Rectangle::draw(){
  cout << "Drawing rectangle" << endl;
  cout << "Dimensions: " << width << " " << height << endl;
}

int Rectangle::getArea(){
  return width * height;
}
```

### 4. Creating Objects<a id="4"></a>

```cpp
#include<iostream>
#include "Rectangle.h"
using namespace std;

int main(){
  // How to create instance of Rectangle class aka object
  Rectangle rectangle;

  // How to access the member of this object using "." dot operator
  rectangle.width = 10;
  rectangle.height = 20;

  cout << rectangle.getArea();

  return 0;
}


/* output
200
*/
```

- Open terminal and type cmd manually

```sh
// to compile
g++ main.cpp Rectangle.cpp -o run.exe

// to run
./run
```

---

- The reason we have separation, or the reason we have two files per class, is to reduce compilation time
- If we create a second rectangle object, that object is going to be an independent instance in the memory

```cpp
#include<iostream>
#include "Rectangle.h"
using namespace std;

int main(){
 Rectangle first;
 Rectangle second;

  // print memory address of first object
  cout << &first << endl;
  cout << &second << endl;
  return 0;

/* output
0x61ff08
0x61ff00
*/

}
```

### 5. Access Modifiers<a id="5"></a>

Principle: Data Hiding
A class should hide its internal data from the outside code and provide **functions** for accessing the data.

### 6. Getters and Setters<a id="6"></a>

- Create Rectangle.h file, and write declaration

```cpp
class Rectangle{
private:
    int width;
    int height;

public:
    void draw();
    int getArea();

    // Getter (accessor)
    int getWidth();

    //Setter (mutator)
    void setWidth(int width);


    // Getter (accessor)
    int getHeight() const;

    // Setter (mutator)
    void setHeight(int height);
};

```

---

- create Rectangle.cpp file and write implementation

```cpp
#include <iostream>
#include "Rectangle.h"

using namespace std;

void Rectangle::draw() {
    cout << "Drawing a rectangle" << endl;
    cout << "Dimensions: " << width << " " << height << endl;
}

int Rectangle::getArea() {
    return width * height;
}

int Rectangle::getWidth() {
    return width;
}

void Rectangle::setWidth(int width) {
    // validate width
    if(width <0)
        throw invalid_argument("width");

    (*this).width = width;
}

int Rectangle::getHeight() const {
    return height;
}

void Rectangle::setHeight(int height){
    this->height = height;
}
```

---

- In main.cpp

```cpp
#include<iostream>
#include "Rectangle.h"

using namespace std;

int main(){

Rectangle rectangle;
rectangle.setWidth(-1);
  return 0;
}


/* output
terminate called after throwing an instance of 'std::invalid_argument'
  what():  width

*/

```

### 7. Constructors<a id="7"></a>

- In Rectangle.h, declare constructor function

```cpp
class Rectangle{
private:
    int width;
    int height;

public:
// How to declare constructor function
    Rectangle(int width, int height);

    void draw();
    int getArea();

    // Getter (accessor)
    int getWidth();

    //Setter (mutator)
    void setWidth(int width);


    // Getter (accessor)
    int getHeight() const;

    // Setter (mutator)
    void setHeight(int height);
};

```

---

- In Rectangle.cpp, write implementation of constructor function

```cpp
//
// Created by Second_Brain on 11/1/2023.
//

#include <iostream>
#include "Rectangle.h"

using namespace std;

void Rectangle::draw() {
    cout << "Drawing a rectangle" << endl;
    cout << "Dimensions: " << width << " " << height << endl;
}

int Rectangle::getArea() {
    return width * height;
}

int Rectangle::getWidth() {
    return width;
}

void Rectangle::setWidth(int width) {
    // validate width
    if(width <0)
        throw invalid_argument("width");

    (*this).width = width;
}

int Rectangle::getHeight() const {
    return height;
}

void Rectangle::setHeight(int height){
    this->height = height;
}

Rectangle::Rectangle(int width, int height) {
    cout << "Constructing  a Rectangle" << endl;
    setWidth(width);
    setHeight(height);
}
```

---

- In main.cpp,

```cpp
#include<iostream>
#include "Rectangle.h"

using namespace std;

int main(){

Rectangle rectangle(10, 20);

cout << rectangle.getWidth();
  return 0;
}



/* output
Constructing  a Rectangle
10
*/
```

### 8. Member Initializer List<a id="8"></a>

- Rectangle.h same

```cpp
//
// Created by Second_Brain on 11/1/2023.
//

#ifndef UNTITLED_RECTANGLE_H
#define UNTITLED_RECTANGLE_H

class Rectangle{
private:
    int width;
    int height;

public:
    Rectangle(int width, int height);

    void draw();
    int getArea();

    // Getter (accessor)
    int getWidth();

    //Setter (mutator)
    void setWidth(int width);


    // Getter (accessor)
    int getHeight() const;

    // Setter (mutator)
    void setHeight(int height);
};

#endif //UNTITLED_RECTANGLE_H

```

---

- In Rectangle.cpp, initialize constructor using member initializer list

```cpp
//
// Created by Second_Brain on 11/1/2023.
//

#include <iostream>
#include "Rectangle.h"

using namespace std;

void Rectangle::draw() {
    cout << "Drawing a rectangle" << endl;
    cout << "Dimensions: " << width << " " << height << endl;
}

int Rectangle::getArea() {
    return width * height;
}

int Rectangle::getWidth() {
    return width;
}

void Rectangle::setWidth(int width) {
    // validate width
    if(width <0)
        throw invalid_argument("width");

    (*this).width = width;
}

int Rectangle::getHeight() const {
    return height;
}

void Rectangle::setHeight(int height){
    this->height = height;
}

//approach1: using () syntax
Rectangle::Rectangle(int width, int height) : width(width), height(height) {
}

//approach2: using {} syntax: moder c++
//Rectangle::Rectangle(int width, int height) : width{width}, height{height} {
//}

```

---

- In main.cpp

```cpp
#include<iostream>
#include "Rectangle.h"

using namespace std;

int main(){

Rectangle rectangle(10, 20);

cout << rectangle.getWidth();
  return 0;
}
```

### 9. The Default Constructor<a id="9"></a>

- In Rectangle.h

```cpp
class Rectangle{
private:
    int width;
    int height;

public:
// default constructor
    Rectangle();
    Rectangle(int width, int height);

    void draw();
    int getArea();

    // Getter (accessor)
    int getWidth();

    //Setter (mutator)
    void setWidth(int width);


    // Getter (accessor)
    int getHeight() const;

    // Setter (mutator)
    void setHeight(int height);
};

```

---

- In Rectangle.cpp

```cpp
#include <iostream>
#include "Rectangle.h"

using namespace std;

void Rectangle::draw() {
    cout << "Drawing a rectangle" << endl;
    cout << "Dimensions: " << width << " " << height << endl;
}

int Rectangle::getArea() {
    return width * height;
}

int Rectangle::getWidth() {
    return width;
}

void Rectangle::setWidth(int width) {
    // validate width
    if(width <0)
        throw invalid_argument("width");

    (*this).width = width;
}

int Rectangle::getHeight() const {
    return height;
}

void Rectangle::setHeight(int height){
    this->height = height;
}

//approach1: using () syntax
Rectangle::Rectangle(int width, int height) : width(width), height(height) {
}

// approach 1: how to create default constructor
Rectangle::Rectangle() {
    //empty
}


```

---

- In main.cpp

```cpp
#include<iostream>
#include "Rectangle.h"

using namespace std;

int main(){

Rectangle rectangle;

cout << rectangle.getWidth();
  return 0;
}
```

### Another way to create default constructor

- In Rectangle.h

```cpp
class Rectangle{
private:
    int width;
    int height;

public:
// How to create default constructor using default keyword
    Rectangle() = default
    Rectangle(int width, int height);

    void draw();
    int getArea();

    // Getter (accessor)
    int getWidth();

    //Setter (mutator)
    void setWidth(int width);


    // Getter (accessor)
    int getHeight() const;

    // Setter (mutator)
    void setHeight(int height);
};

```

---

- In Rectangle.cpp

```cpp
#include <iostream>
#include "Rectangle.h"

using namespace std;

void Rectangle::draw() {
    cout << "Drawing a rectangle" << endl;
    cout << "Dimensions: " << width << " " << height << endl;
}

int Rectangle::getArea() {
    return width * height;
}

int Rectangle::getWidth() {
    return width;
}

void Rectangle::setWidth(int width) {
    // validate width
    if(width <0)
        throw invalid_argument("width");

    (*this).width = width;
}

int Rectangle::getHeight() const {
    return height;
}

void Rectangle::setHeight(int height){
    this->height = height;
}

//approach1: using () syntax
Rectangle::Rectangle(int width, int height) : width(width), height(height) {
}

// approach 1: how to create default constructor
Rectangle::Rectangle() {
    //empty
}


```

---

- In main.cpp

```cpp
#include<iostream>
#include "Rectangle.h"

using namespace std;

int main(){

Rectangle rectangle;

cout << rectangle.getWidth();
  return 0;
}
```

### 10. Using the Explicit Keyword<a id="10"></a>

- Person.h

```cpp
class Person{

private:
    int age;

public:
    //constructor
    explicit Person(int age);


};

```

---

- Person.cpp

```cpp
#include "Person.h"

Person::Person(int age):age{age}{

}
```

---

- main.cpp

```cpp
#include <iostream>
#include "Person.h"

void showPerson(Person person){
}

int main() {
    Person person(10);
//    Person person{10};

    showPerson(person);
    return 0;
}

```

### 11. Constructor Delegation<a id="11"></a>

- Rectangle.h

```cpp
#include <string>

using namespace std;

class Rectangle{
private:
    int width;
    int height;
    string color;

public:
// default constructor
    Rectangle();
    Rectangle(int width, int height);

    Rectangle(int width, int height, const string& color);


    void draw();
    int getArea();

    // Getter (accessor)
    int getWidth();

    //Setter (mutator)
    void setWidth(int width);


    // Getter (accessor)
    int getHeight() const;

    // Setter (mutator)
    void setHeight(int height);
};

```

---

- Rectangle.cpp

```cpp
#include <iostream>
#include "Rectangle.h"

using namespace std;

void Rectangle::draw() {
    cout << "Drawing a rectangle" << endl;
    cout << "Dimensions: " << width << " " << height << endl;
}

int Rectangle::getArea() {
    return width * height;
}

int Rectangle::getWidth() {
    return width;
}

void Rectangle::setWidth(int width) {
    // validate width
    if(width <0)
        throw invalid_argument("width");

    (*this).width = width;
}

int Rectangle::getHeight() const {
    return height;
}

void Rectangle::setHeight(int height){
    this->height = height;
}

//approach1: using () syntax
Rectangle::Rectangle(int width, int height) : width(width), height(height) {
}

// approach 1: how to create default constructor
Rectangle::Rectangle() {
    //empty
}

Rectangle::Rectangle(int width, int height, const string& color):Rectangle() {
    cout << "constructing a Rectangle with color";
    this->color = color;
}
```

---

- main.cpp

```cpp
#include<iostream>
#include "Rectangle.h"

using namespace std;

int main(){

Rectangle rectangle(10, 20, "blue");

//Rectangle rectangle{10, 20, "blue"};

cout << rectangle.getWidth();
  return 0;
}
```

### 12. The Copy Constructor<a id="12"></a>

- Rectangle.h

```cpp
#include <string>

using namespace std;

class Rectangle{
private:
    int width;
    int height;
    string color;

public:
// default constructor
    Rectangle();
    Rectangle(int width, int height);

    Rectangle(int width, int height, const string& color);


    void draw();
    int getArea();

    // Getter (accessor)
    int getWidth();

    //Setter (mutator)
    void setWidth(int width);


    // Getter (accessor)
    int getHeight() const;

    // Setter (mutator)
    void setHeight(int height);
};

```

---

- Rectangle.cpp

```cpp

#include <iostream>
#include "Rectangle.h"

using namespace std;

void Rectangle::draw() {
    cout << "Drawing a rectangle" << endl;
    cout << "Dimensions: " << width << " " << height << endl;
}

int Rectangle::getArea() {
    return width * height;
}

int Rectangle::getWidth() {
    return width;
}

void Rectangle::setWidth(int width) {
    // validate width
    if(width <0)
        throw invalid_argument("width");

    (*this).width = width;
}

int Rectangle::getHeight() const {
    return height;
}

void Rectangle::setHeight(int height){
    this->height = height;
}

//approach1: using () syntax
Rectangle::Rectangle(int width, int height) : width(width), height(height) {
}

// approach 1: how to create default constructor
Rectangle::Rectangle() {
    //empty
}

Rectangle::Rectangle(int width, int height, const string& color):Rectangle() {
    cout << "constructing a Rectangle with color";
    this->color = color;
}
```

---

- main.cpp

```cpp
#include<iostream>
#include "Rectangle.h"

using namespace std;

int main(){

Rectangle first(10, 20);

Rectangle second = first;

  return 0;
}
```

### 13. The Destructor<a id="13"></a>

- Rectangle.h

```cpp
#include<iostream>
#include "Rectangle.h"

using namespace std;

int main(){

Rectangle first(10, 20);

  return 0;
}
```

---

- Rectangle.cpp

```cpp
#include <string>

using namespace std;

class Rectangle{
private:
    int width;
    int height;
    string color;

public:
    Rectangle();
    Rectangle(int width, int height);
    // how to define destructor
    ~Rectangle();

    Rectangle(int width, int height, const string& color);


    void draw();
    int getArea();

    // Getter (accessor)
    int getWidth();

    //Setter (mutator)
    void setWidth(int width);


    // Getter (accessor)
    int getHeight() const;

    // Setter (mutator)
    void setHeight(int height);
};

```

---

- main.cpp

```cpp
#include<iostream>
#include "Rectangle.h"

using namespace std;

int main(){

Rectangle first(10, 20);

  return 0;
}

/* output
Destructor called
*/
```

### 14. Static Members<a id="14"></a>

- Rectangle.h

```cpp
#include <string>

using namespace std;

class Rectangle{
private:
    int width;
    int height;
    string color;

public:
    // how to declare static member
    static int objectsCount;

    Rectangle();
    Rectangle(int width, int height);
    Rectangle(int width, int height, const string& color);

    ~Rectangle();

    void draw();
    int getArea();

    // Getter (accessor)
    int getWidth();

    //Setter (mutator)
    void setWidth(int width);


    // Getter (accessor)
    int getHeight() const;

    // Setter (mutator)
    void setHeight(int height);
};

```

- Rectangle.cpp

```cpp
//
// Created by Second_Brain on 11/1/2023.
//

#include <iostream>
#include "Rectangle.h"

using namespace std;

void Rectangle::draw() {
    cout << "Drawing a rectangle" << endl;
    cout << "Dimensions: " << width << " " << height << endl;
}

int Rectangle::getArea() {
    return width * height;
}

int Rectangle::getWidth() {
    return width;
}

void Rectangle::setWidth(int width) {
    // validate width
    if(width <0)
        throw invalid_argument("width");

    (*this).width = width;
}

int Rectangle::getHeight() const {
    return height;
}

void Rectangle::setHeight(int height){
    this->height = height;
}

// static member
Rectangle::Rectangle(int width, int height) {
objectsCount++;
cout << "Constructing a rectangle" << endl;
    setHeight(height);
    setWidth(width);
}

// approach 1: how to create default constructor
Rectangle::Rectangle() {
    //empty
}

Rectangle::Rectangle(int width, int height, const string& color):Rectangle() {
    cout << "constructing a Rectangle with color";
    this->color = color;
}

Rectangle::~Rectangle() {
    cout << "Destructor called" << endl ;
}

int Rectangle::objectsCount = 0;
```

---

- main.cpp

```cpp
#include<iostream>
#include "Rectangle.h"

using namespace std;

int main(){

Rectangle first(10, 20);
Rectangle second(10, 20);

cout << Rectangle::objectsCount << endl;

  return 0;
}
```

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

- protected member
- virtual method
- method overriding
- abstract classes
- final classes

### 34. Inheritance<a id="34"></a>

Inheritance is a mechanism for re-using code, so we can implement common feature from one class to other classes

<img src="notes/inheritance.png" width="400">

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
