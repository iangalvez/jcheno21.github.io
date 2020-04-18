## Lecture 4 Notes
For a **pdf version** of these notes, click [here](./Lecture 4 Notes.pdf).

---

* Recall the **if-ladder** from the last lecture:


```cpp
if (income < 30000)
  cout << "Low";
else 
{
  if (income >= 30000 && income < 100000)
    cout << "Middle";
  else
  {
    if (income >= 100000 && income < 500000)
      cout << "High";
    else
      cout << "Very high";
}}
```

* The if-ladder can get really messy, so pay extra attention to the number and relative positions of <code>if</code> and <code>else</code>

<br>

**Switch Statements**

* Let's say we have a program that asks the user to make a choice from one to five:

 
```cpp
int main()
{
  ...
  int choice;
  cin >> choice;
  if (choice == 1)
    cout << "Do thing A" << endl;
  else if (choice == 2 || choice == 4)
    cout << "Do thing B" << endl;
  else if (choice == 3 || choice == 5)
    cout << "Do thing C" << endl;
  else
  {
    cout << "Choice must be 1 through 5." << endl;
    cout << "I'll assume you wanted choice 1" << endl;
    cout << "Do thing A" << endl;
  }
  ...
}
``` 

<br>
* There's a more convenient way to write the code above:


```cpp
int main()
{
  ...
  int choice;
  cin >> choice;
  
  // Switch Statement
  switch (choice)
  {
    // Equivalent to saying 'if (choice == 1)'
    case 1:
      cout << "Do thing A" << endl;
      break;
      
    // Equivalent to saying 'if (choice == 2 || choice == 4)'
    case 2:
    case 4:
      cout << "Do thing B" << endl;
      break;
      
    case 3:
    case 5:
      cout << "Do thing B" << endl;
      break;
      
    // This is used when your input does not match any of the cases
    default:
      cout << "Choice must be 1 through 5." << endl;
      cout << "I'll assume you wanted choice 1" << endl;
      cout << "Do thing A" << endl;
      break; // This 'break' is optional since it is at the bottom of the switch statement anyways
  }
  ...
}
``` 
<br>

- This is called a <b>switch statement</b>

  - Initiate it with <code>switch (variableName)</code>, followed by curly braces
  
    - <code>variableName</code> is the name you defined as an int<br>
     
     
    
  - Write out <code>case</code>, followed by the specific number you want to assign to it
  
  - If another number satisfies the same condition, write it as a separate case on the next line
  
  - <code>break</code> tells the program to ignore everything else that comes afterwards <i>within</i> the switch statement
  
  - If the int does not match any of the cases, it will jump to the <code>default</code> section
  
<br>

**Frequently Asked Questions**

- **What happens if you accidentally forgot to include a break?**

  - The program will run the code for subsequent cases until it sees another <code>break</code><br>
   
- **Could you use a range of numbers for cases?**

  - No, you need to type each case separately<br>
   
- **Could you use <code>></code> or <code><</code> signs for cases?**
  
  - No, you can only assign a certain case to a specific integer
   
- **Could you use a switch for strings or doubles?**

  - No, you can only use integers<br>

<br>

In summary, **switch statements** are an alternate way to write if-statements. Although they are clearer to read, they are very limited and only work with integers.

<br>

**While-Loops**

* Let's say I want a program that will output the following:
```
How many times do you want to be greeted? 3
Hello
Hello
Hello
```
* We could write plenty of if-statements, but this is not practical for large numbers:
```cpp
cout << "How many times do you want to be greeted> ";
int nTimes;
cin >> nTimes;

  if (nTimes >= 1);
    cout << "Hello" << endl;
  if (nTimes >= 2);
    cout << "Hello" << endl;
  if (nTimes >= 3);
    cout << "Hello" << endl;
  if (nTimes >= 4);
    cout << "Hello" << endl;
  if (nTimes >= 5);
    cout << "Hello" << endl;
```

- Instead, we can use a **while-statement**, which is very similar to an if-statement

  - The difference is that if-statements only execute the program once
  
  - While-statements **loop back** and check the original condition again until it is no longer true


* Now, the program is as follows:

```cpp
cout << "How many times do you want to be greeted> ";
int nTimes;
cin >> nTimes;  // Let's say we want to be greeted 3 times
  
int n = 1; 
while (n <= nTimes)
{
  cout << "Hello" << endl;
  n = n + 1 // Reassigns n and loops back to the beginning of the while-statement
}
```
<br>

**Shorthands for Assignment Statements**

- These assignment statements are particularly useful for loops, and can be condensed as follows
  - <code>n = n + 1</code> becomes <code>n += 1</code>
  - <code>m = m * 2</code> becomes <code>m *= 2</code>
  - <code>k = k / 10</code> becomes <code>k /= 10</code>

<br>

- There are even shorter ways to write the same thing
  - <code>n++</code> = <code>++n</code> = <code>n += 1</code> = <code>n = n + 1</code>
  - <code>n--</code> = <code>--n</code> = <code>n -= 1</code> = <code>n = n - 1</code>
  
<br>

- Pay attention to <code><</code> vs. <code><=</code> **and** <code>></code> vs. <code>>=</code> when writing loops
  - They can cause you calculations to be off by one
  
<br>

* Let's consider an **infinite loop**, such that there is no assignment statement at the end

```cpp
int n = 1;
while (n <= 10)
{
...
...
...
...
...
}
```

* The variable <code>n</code> will be the same every time, so the loop goes on forever

* If you run an infinite loop, you need to close the window or hit <code>Ctrl+C</code> to exit out of the program

<br>

**For Loops**

* There is another type of loop called a **for-loop**

```cpp
for (int n = 1; n <= nTimes; n++)
  cout << "Hello" << endl;
  ...
```

- It has the following syntax:
```cpp
for (initialization; stay_In_Loop_Condition; prepare_For_Next_Iteration)
  statement
  ...
```

* The advantage of a for-loop is that all the necessary components are set up at the top of the command

- You can still have an infinite loop

  - In the example below, our "prepare-for-next-iteration" is set so that <code>k</code> gets added by 1
  
  - This will always satisfy the "stay-in-loop" condition
  
  - The computer will perform this operation until it hits 1 billion, the largest value for an int

```cpp
for (int k = 10; k >= 0; k++)
  cout << k << endl;
  ...
```

<br>

**Example**

* The following program writes out the powers of 2 that are less than 1000, starting at 1

```cpp
for (int n = 1; n < 1000; n *= 2)
  cout << n << endl;
```

* The output will look like
```
1
2
4
8
16
32
64
128
256
512
```

[back](./)
