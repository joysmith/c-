| feature                           | feature                  |
| --------------------------------- | ------------------------ |
| 1. [Getting Started with C++](#1) | 4. [Decision Making](#4) |
| 2. [Basics feature](#2)           | 5. [Loops](#5)           |
| 3. [Fundamental Data Types](#3)   | 6. [Functions](#6)       |

---

#### 1. [Getting Started with C++](#01)<a id="1"></a>

#### 2. [Introduction to C++](#02)

#### 3. [Popular IDEs](#03)

#### 4. [Your First C++ Program](#04)

#### 5. [Compiling and Running a C++ Program](#05)

#### 6. [Changing the Theme](#06)

---

#### 7. [Basics Introduction](#07)<a id="2"></a>

#### 8. [Variables](#08)

#### 9. [Constants](#09)

#### 10. [Naming Conventions](#010)

#### 11. [Mathematical Expressions](#011)

#### 12. [Order of Operators](#012)

#### 13. [Writing Output to the Console](#013)

#### 14. [Reading from the Console](#014)

#### 15. [Working with the Standard Library](#015)

#### 16. [Comments](#016)

---

#### 17. [Fundamental Data Types Introduction](#017)<a id="3"></a>

#### 18. [Fundamental Data Types](#018)

#### 19. [Initializing Variables](#019)

#### 20. [Working with Numbers](#020)

#### 21. [Narrowing](#021)

#### 22. [Generating Random Numbers](#022)

#### 23. [Formatting Output](#023)

#### 24. [Data Types Size and Limits](#024)

#### 25. [Working with Booleans](#025)

#### 26. [Working with Characters and Strings](#026)

#### 27. [Working with Arrays](#027)

#### 28. [Type Conversion](#028)

---

#### 29. [Decision Making Introduction](#029)<a id="4"></a>

#### 30. [Comparison Operators](#030)

#### 31. [Logical Operators](#031)

#### 32. [Order of Logical Operators](#032)

#### 33. [If Statements](#033)

#### 34. [Nested If Statements](#034)

#### 35. [The Conditional Operator](#035)

#### 36. [The Switch Statement](#036)

---

#### 37. [Loops Introduction](#037)<a id="5"></a>

#### 38. [The for Loop](#038)

#### 39. [Range-based for Loops](#039)

#### 40. [While Loops](#040)

#### 41. [Do-while Loops](#041)

#### 42. [Break and Continue Statements](#042)

#### 43. [Nested Loops](#043)

---

#### 44. [Functions Introduction](#044)<a id="6"></a>

#### 45. [Defining and Calling Functions](#045)

#### 46. [Parameters with a Default Value](#046)

#### 47. [Overloading Functions](#047)

#### 48. [Passing Arguments by Value or Reference](#048)

#### 49. [Local vs Global Variables](#049)

#### 50. [Declaring Functions](#050)

#### 51. [Organizing Functions in Files](#051)

#### 52. [Using Namespaces](#052)

#### 53. [Debugging C++ Programs](#053)

---

# The Basics feature

### 1. Introduction<a id="07"></a>

### 2. Variables<a id="08"></a>

```cpp
#include <iostream>
using namespace std;

int main() {
  // approach 1: declaring variable then initializing
  int audio_file_size;
  audio_file_size = 100;

  // approach 2: combine two statements in single line -declaration & initialization
  int image_file_size = 5;

  cout << image_file_size;
  return 0;
}
```

### 3. Constants<a id="09"></a>

When we don't want value of variable to change we use constant

```cpp
#include <iostream>
using namespace std;

int main() {
  // How to use constant
  const double pi = 3.14;

  cout << pi;
  return 0;
}
```

### 4. Naming Conventions<a id="010"></a>

```cpp
#include <iostream>
using namespace std;

int main() {

  // Camel Case
  int myFileSize = 12;

  // Snake Case
  int my_file_size = 14;

  // Pascal Case
  int MyFileSize = 13;

  return 0;
}
```

### 5. Mathematical Expressions<a id="011"></a>

```cpp
#include <iostream>
using namespace std;

int main() {

  int x = 5;
  int y = 10;

  // operator +, -, /, *
  // operands x y on which we are performing operations using operator
  int z = x + y;

  cout << z;

  return 0;
}

```

---

````cpp
#include <iostream>
using namespace std;

int main() {

  double x = 10;
  double y = 3;

  // operator +, -, /, *
  // operands x y
  double z = x / y;

  cout << z;

  return 0;
}

---

Postfix

```cpp
#include <iostream>
using namespace std;

int main() {

int x = 10;
// first store x value in y then increment by 1
int y = x ++;
cout << "x: " << x << endl;
cout << "y: " << y ;
  return 0;
}

/* output
x: 11
y: 10
*/

````

---

Prefix

```cpp
#include <iostream>
using namespace std;

int main() {

int x = 10;
// first increment x by 1 then store value in y
int y = ++x;
cout << "x: " << x << endl;
cout << "y: " << y ;
  return 0;
}

/* output
x: 11
y: 11
*/

```

### 6. Order of Operators<a id="012"></a>

```cpp
#include <iostream>
using namespace std;

int main() {
// PEMDAS math rule
// priority: (), * and /, + and  -
double x = 1 + 2 * 5;
cout << "X: " << x;

return 0;
}

/* output
X: 7
*/
```

---

```cpp
#include <iostream>
using namespace std;

int main() {
// priority: (), * and /, + and  -
double x = 10;
double y = 5;
double z = (x + 10) / (3 * y);

cout << "z: " << z;

return 0;
}

/* output
z: 1.33333
*/
```

### 7. Writing Output to the Console<a id="013"></a>

"<<" stream insertion operator: It is an operator for inserting something to our output stream  
"cout" is an object that represent standard output stream

The standard output is our console or terminal window, so using cout we can write a sequence of character on standard output which is our standard window or terminal

```cpp
#include <iostream>
using namespace std;

int main() {
int x = 10;

// single statement
cout << x;

// combining statement into single statement by chaining multiple string insertion operators
cout << "x: " << x;

return 0;
}

/* output
10x: 10
*/
```

---

endl: end of line

```cpp
#include <iostream>
using namespace std;

int main() {
int x = 10;
int y = 20;

// How to move in next line using "endl" manipulator
cout << "x: " << x << endl;
cout << "y: " << y << endl;

return 0;
}

/* output
x: 10
y: 20
*/
```

### 8. Reading from the Console<a id="014"></a>

">>" string extraction operator

```cpp

#include <iostream>
using namespace std;

int main() {
cout << "Enter a value: ";
int value;

// ">>" string extractor operator
// reading data from console and putting it in value variable
cin >> value;

// How to move in next line using "endl" manipulator
cout << "value: " << value << endl;

return 0;
}

/* output
Enter a value: 7
value: 7
*/
```

---

```cpp
#include <iostream>
using namespace std;

int main() {
cout << "Enter a value for x and y: " << endl;
double x;
double y;

cin >> x;
cin >> y;

cout << "sum is: " << x + y;

return 0;
}

/* output
Enter a value for x and y:
55
22
sum is: 77
*/

```

Chaining string extraction operator

```cpp
#include <iostream>
using namespace std;

int main() {
cout << "Enter a value for x and y: " << endl;
double x;
double y;

// chaining string extraction operator
cin >> x >> y;

cout << "sum is: " << x + y;

return 0;
}

/* output
Enter a value for x and y:
2
5
sum is: 7
*/

```

### 9. Working with the Standard Library<a id="015"></a>

[floor function usage ref](https://cplusplus.com/reference/cmath/floor/)

```cpp
#include <iostream>
#include <cmath>
using namespace std;

int main() {
// the floor() function takes 1 args/input
double result = floor(1.3);

cout << "result: " <<result;

return 0;
}

/* output
result: 1
*/
```

---

[pow function usage ref](https://cplusplus.com/reference/cmath/pow/)

```cpp
#include <iostream>
#include <cmath>
using namespace std;

int main() {
// 2^3: 2 to the power of 3
// 2 x 2 x 2 = 8
// the pow() function takes 2 args/inputs: one is the base and another one as exponent/power
double result = pow(2, 3);

cout << "result: " <<result;

return 0;
}

/* output
result: 8
*/
```

### 10. Comments<a id="016"></a>

Comment: To clarify our code to make code more understandable, they are ignored by compiler which means they are not compiled by compiler

comment always Why & How, not what

```cpp
#include <iostream>

using namespace std;

int main() {
// Single line comment

/*
M
u
l
t
i
l
i
n
e

c
o
m
m
e
n
t
*/

return 0;
}
```

<br>

# Fundamental Data Types

### 11. Introduction<a id="017"></a>

c++ is statically typed language:  
When we declare a variable we need to specify its type and this type could not change through the lifetime of our program  
other language resemble same feature: c++, java, C#, Type script

Dynamically typed language:  
Python, Javascript, Ruby: These language we don't have to give our variable a particular type like int, boolean, string, bool etc, The type will be determined based on the value that we will assign to this variable and that type can change throughout the life time of out program

### 12. Fundamental Data Types<a id="018"></a>

> Whole number

| Type      | Bytes |           range |
| :-------- | :---: | --------------: |
| short     |   2   | -32768 to 32767 |
| int       |   4   |       -2B to 2B |
| long      |   4   |       -2B to 2B |
| long long |   8   |                 |

---

<br>

> Decimal number

| Type        | Bytes |                range |
| :---------- | :---: | -------------------: |
| float       |   4   |                      |
| double      |   8   |  -1.7E308 to 1.7E308 |
| long double |   8   | -3.4E932 to 1.7E4832 |

---

| Type | Bytes |      range |
| :--- | :---: | ---------: |
| bool |   1   | true/false |
| char |   1   |      ascii |

### 13. Initializing Variables<a id="019"></a>

Why we write f/F or l/L after value as suffix ?  
To force compiler to take as long or float we write f/F or l/L at the end of value in uppercase or lowercase

```cpp

#include <iostream>

using namespace std;

int main() {
float interestRate = 3.67f;
float newInterestRate = 3.67F;
double price = 99.9;
long movieSize = 1000000l;
long audioSize = 1000000L;
bool isGameOVer = false;

return 0;
}

```

---

auto keyword: using auto keyword compiler know type because of f/F, l/L, false, "c" etc otherwise it will set type in default like int, double

```cpp
#include <iostream>

using namespace std;

int main() {
// compile will take type as float
auto interestRate = 3.67f;
auto newInterestRate = 3.67F;

// compile will take type as double
auto price = 99.9;

// compile will take type as long
auto movieSize = 1000000l;
auto audioSize = 1000000L;

// compile will take type as bool
auto isGameOVer = false;

// compile will take type as char
auto letter = "j";

return 0;
}
```

---

{} brace initializer: this will set value to 0 when empty, instead of any garbage value

```cpp
#include <iostream>

using namespace std;

int main() {
// brace initialized when empty
int number {};

 // brace initialized with value
int number2 {7};

cout << "default value: "<<number;
cout << "initialize value: "<<number2;

return 0;
}


/* output
default value: 0
initialize value: 7
*/
```

### 14. Working with Numbers<a id="020"></a>

| System                |  Digits  | Example |
| :-------------------- | :------: | ------: |
| Decimal (Base 10)     |   0-9    |     255 |
| Binary (Base 2)       |   0-1    |  111111 |
| Hexadecimal (Base 16) | 0-9, A-F |      FF |

```cpp
#include <iostream>

using namespace std;

int main() {
int number = 255;
int numberBinary = 0b11111111;
int numberHexa = 0xff;

cout << "number: "<< number << endl;
cout << "numberBinary: "<< numberBinary << endl;
cout << "numberHexa: "<< numberHexa << endl;

return 0;
}


/* output
number: 255
numberBinary: 255
numberHexa: 255
*/

```

### 15. Narrowing<a id="021"></a>

```cpp

#include <iostream>

using namespace std;

int main() {
int number = 1'000'000;
// narrowing conversion cause data loss
short another = number;

cout << "another: "<< another << endl;

return 0;
}



/* output
number: 16960
*/
```

### 16. Generating Random Numbers<a id="022"></a>

### 17. Formatting Output<a id="023"></a>

### 18. Data Types Size and Limits<a id="024"></a>

### 19. Working with Booleans<a id="025"></a>

sticky manipulator: once you applied you will receive all value of the same type for instance boolalpha gives you false

```cpp
#include <iostream>

using namespace std;

int main() {
bool isNewUser = false;
cout << "isNewUser: " << isNewUser << endl;

// using sticky string boolalpha manipulator
// after this all boolean value display as false instead of 0
cout << boolalpha << "isNewUser: " << isNewUser;

return 0;
}



/* output
isNewUser: 0
isNewUser: false
*/
```

### 20. Working with Characters and Strings<a id="026"></a>

```cpp
#include <iostream>

using namespace std;

int main() {
char ch = 'a';

// dispaly character
cout << ch << endl;

// display ascii character code
cout << +ch << endl;

// BAD practise using ascii code for initialization
char newch = 98;
cout << ch;

return 0;
}



/* output
a
97
a
*/
```

---

```cpp
#include <iostream>

using namespace std;

int main() {
string movie = "Spider Man";
cout << movie << endl;

// reading string from terminal without space
string name;
cout << "Enter your full name with space: ";
cin >> name;
cout << "Hi " << name;

return 0;
}


/* output
Spider Man
Enter your full name with space: Gta san andreas
Hi Gta
*/
```

---

```cpp
#include <iostream>

using namespace std;

int main() {

// reading string from terminal with space
string name;
cout << "Enter your full name with space: ";
getline(cin, name);
cout << "Hi " << name;

return 0;
}



/* output
Enter your full name with space: Tony stark
Hi Tony stark
*/
```

### 21. Working with Arrays<a id="027"></a>

### 22. Type Conversion<a id="028"></a>

<br>

# Decision Making

### 23. Introduction<a id="029"></a>

### 24. Comparison Operators<a id="030"></a>

### 25. Logical Operators<a id="031"></a>

### 26. Order of Logical Operators<a id="032"></a>

### 27. If Statements<a id="033"></a>

### 28. Nested If Statements<a id="034"></a>

### 29. The Conditional Operator<a id="035"></a>

### 30. The Switch Statement<a id="036"></a>

<br>

# Loops

### 31. Introduction<a id="037"></a>

### 32. The for Loop<a id="038"></a>

### 33. Range-based for Loops<a id="039"></a>

### 34. While Loops<a id="040"></a>

### 35. Do-while Loops<a id="041"></a>

### 36. Break and Continue Statements<a id="042"></a>

### 37. Nested Loops<a id="043"></a>

<br>

# Functions

### 38. Introduction<a id="044"></a>

### 39. Defining and Calling Functions<a id="045"></a>

1. Function without input

```cpp
#include <iostream>
using namespace std;

// Defining function
void greet(){
cout << "Hello World" << endl;
}

int main() {
// Calling -invoking -executing function
greet();

cout << "Done!!!";
return 0;
}



/* output
Hello World
Done!!!
*/
```

### 40. Parameters with a Default Value<a id="046"></a>

2. Function with input

difference b/w parameter vs argument

```cpp
#include <iostream>
using namespace std;

// when defining a function we  declare parameter
void greet(string firstName, string lastName){
cout << "Hello " << firstName << " " << lastName << endl;
}

int main() {
// Calling -invoking -executing function
// when calling a function we pass arguments
greet("Sam", "Altman");

cout << "Done!!!";
return 0;
}


/* output
Hello Sam Altman
Done!!!
*/
```

---

3. Function with output aka return type

```cpp
#include <iostream>
using namespace std;

// defining return type function aka function with output
string fullName(string firstName, string lastName){
// concatenating or combining string using '+' operator
return firstName + " " + lastName;
}

int main() {
// calling function then, storing info in name variable
string name = fullName("Joy", "Peter");
cout << name << endl;

cout << "Done!!!";
return 0;
}



/* output
Joy Peter
Done!!!
*/
```

---

Parameter with default value

```cpp
#include <iostream>
using namespace std;

// default tax rate is set to 20%
double claculateTax(double income, double taxRate = .2){
  return income * taxRate;
}

int main() {
// tax rate 20%
double tax = claculateTax(10000);

// tax rate 30%
// note the 2nd args will override the default parameter value
double tax2 = claculateTax(10000, .3);

cout << tax << endl;
cout << tax2 << endl;


cout << "Done!!!";
return 0;
}



/* output
2000
3000
Done!!!
*/
```

note-
parameter with default comes after the parameter without default value.
calculateTax(10000, .3:comes after default)

### 41. Overloading Functions<a id="047"></a>

Signature of function: name of fun + (no. of parameter and type of parameter)

never make same signature function that will cause compiler to make error

Version 1 function signature

- name of function: greet
- no. of parameter: 1
- type of parameter: string

<br>

Version 2 function signature

- name of function: greet
- no. of parameter: 2
- type of parameter: string, string

```cpp
#include <iostream>
using namespace std;

// 1st version
void greet(string name){
cout << "Hello " << name << endl;
}

// 2nd version
void greet(string title, string name){
cout << "Hello " << title << " " << name;
}


int main() {
greet("Joy");
greet("Mr", "Joy");

return 0;
}


/* output
Hello Joy
Hello Mr Joy
*/
```

### 42. Passing Arguments by Value or Reference<a id="048"></a>

Passing Arguments by Value

```cpp
#include <iostream>
using namespace std;

double increasePrice(double price){
price = price * 1.2;
// price *= 1.2;
return price;
}


int main() {
double price = 100;

// copy of price-value is passed to function which would use memory
price = increasePrice(price);
cout << price;
return 0;
}


/* output
120
*/

```

---

Passing Arguments by Reference

When we have large no. of data for processing, copy by value is bit expensive in term of memory so we pass by reference i.e location of memory

```cpp

#include <iostream>
using namespace std;

// &: a reference or address operator
void increasePrice(double& price){
price = price * 1.2;
// price *= 1.2;
}


int main() {
double price = 100;

// ref of price-value is passed to function which won't use memory
increasePrice(price);
cout << price;
return 0;
}


/* output
120
*/
```

---

Second example passing arguments by Reference

```cpp
#include <iostream>
using namespace std;

// &: a reference or address operator
void greet(string& name){
cout << "Hello " << name;
}


int main() {
string name = "Joy";
// passing address or references
greet(name);

return 0;
}



/* output
Hello Joy
*/
```

### 43. Local vs Global Variables<a id="049"></a>

```cpp
#include <iostream>
using namespace std;

// Global variable (global scope)
double taxRate = .2;


double calculateTax(int sales){
// accessing global variable
return sales * taxRate;
}


int main() {
// local variable (local scope)
int sales = 10000;

double tax = calculateTax(sales);
cout << tax;

return 0;
}


/* output
2000
*/
```

### 44. Declaring Functions<a id="050"></a>

1. We always define our function before main function
1. In case we need to define our custom function after main function, then we declare the function before then main function.
1. This tell the compiler there is function that exist and is somewhere else
1. we tell compiler there is a greet function with datatype string, with name parameter, and it is somewhere else.

```cpp
#include <iostream>
using namespace std;

// function declaration or function prototype
void greet(string name);

int main() {
greet("joy");

return 0;
}

// function definition or implementation
void greet(string name){
cout << "Hello " << name;
}


/* output
Hello joy
*/
```

### 45. Organizing Functions in Files<a id="051"></a>

### 46. Using Namespaces<a id="052"></a>

### 47. Debugging C++ Programs<a id="053"></a>
