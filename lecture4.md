## Lecture 4 Notes

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

* The <b>if-ladder</b> can get really messy, so pay extra attention to the number and relative positions of <code>if</code> and <code>else</code>

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

- This is called a <b>switch statement</b>
  - Initiate it wiith <code>switch (variableName)</code> followed by curly braces
  - Write out <code>case</code>, followed by the integer you want to assign to it
  - If there is another integer that satisfies the same condition, write it as another case immediately following the previous case
  - <code>break</code> tells the program to ignore everything else that comes afterward <i>within</i> the switch statement
  - If the int does not match any of the cases, it will jump to the <code>default</code> section</li>
<br>

**Frequently Asked Questions**

- What happens if you accidentally forgot to include a <b>break</b>?
  - The program will run the code for subsequent cases until it sees another <code>break</code>

- Could you use a **range of numbers** for cases?
  - No, you need to type each case separately

- Could you use <code>></code> or <code><</code> signs for cases?
  - No, you can only assign a certain case to a specific integer
  
- Could you use a switch for **strings or doubles**?
  - No, you can only use integers

   

[back](./)
