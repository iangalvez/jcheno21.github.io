For a **pdf version** of Lecture 1 notes, click [here](./Lecture 1 Notes.pdf).

---

## Introduction to Programming

* We want a program what will do the following calculations

```
How many hours did you work? 40
What is your hourly rate of pay? 16.13

You earned $645.20
$64.52 will be withheld.
```

* The program is as follows

```cpp
#include <iostream>
using namespace std;

int main()
{
  cout << "How many hours did you work? ";
  double hoursworked;
  cin >> hoursworked;

  cout << "What is your hourly rate of pay? ";
  double payRate;
  cin >> payRate;

  double amtEarned = hoursworked * payRate;
  cout.setf(ios::fixed);
  cout.precision(2);
  cout << "You earned $" << amtEarned << endl;
  cout << "$" << (0.10 * amtEarned) << " will be withheld." << endl;
}
```

* Along the way, you can run the following to see if the computer registered the correct inputs

```cpp
cout << "hours worked is " << hoursworked << endl;
cout << "pay rate is " << payRate << endl;
```

* Note that <code>endl</code> stands for “end line” and is used to move onto the next line

- #include <iostream> allows the C++ compiler to use <code>cin</code> and <code>cout</code>
  
  - These are the input and output streams

* <code>std</code> stands for the standard library


## Identifiers

- There are two ways to declare identifiers:
  - <code>type identifier;</code>
  - <code>type identifier = expression;</code>


- Rules for identifiers:

  - The first character must be a letter, either uppercase or lowercase

  - Any subsequent characters are optional, but can be a letter, digit, or underscore

- Examples:
  - <code>fred</code>
  - <code>covid19</code>
  - <code>covid_19</code>
  - <code>hours_worked</code>
  - <code>hoursworked</code>

## Types

- <code>double</code> is used to define values that hold numbers with decimal points

  - Can be positive, negative, or zero
  
  - 15 to 16 decimal digits of precision
  
  - From 10<sup>-308</sup> to 10<sup>308</sup>


* <code>int</code> is used to define whole numbers from -2 billion to 2 billion


* The following code tells the program that all subsequent outputs are to be 2 decimal places in precision

```cpp
cout.setf(ios::fixed);
cout.precision(2);
```

## Mathematics

* Most order of operations PEMDAS from algebra carry over to C++

* Multiplication and division have higher precedence than addition and subtraction

* Operators with equal precedence are read from left to right

- However, the star operator must be used for multiplication

  - <code>2(3+5)</code> must be written as <code>2*(3+5)</code>

- Four possible cases for division operations, and one case for the remainder modulus:

  - Double ÷ Double = Double <br> <code>14.3/5.0 = 2.86</code>

  - Double ÷ Int = Double <br> <code>8.65/3 = 2.8833</code>

  - Int ÷ Double = Double <br> <code>14/5.0 = 2.8</code>
  
  - Int ÷ Int = Int <br> <code>14/5 = 2</code>

  - Remainder Modulus <br> <code>14%5 = 4</code>

* Most compilers will restrict outputs to four decimal places

* If less than four decimal places, doubles will be truncated to the last nonzero digit

## Logic Errors

* The following examples are logic errors:

* Sometimes, there might be a 0 in the denominator, and the program might crash

```cpp
int a = 10;
int b = a * a;
int c = 25 / (b-100);
```

* The following example is undefined because e is one billion and f exceeds the maximum value allowed for an int

*  The output is some random integer

```cpp
int d = 1000;
int e  = d * d * d;
int f = d * e;
```

  
[back](./)
