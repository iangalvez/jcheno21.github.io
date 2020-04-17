## Lecture 4 Notes
<br>

* Recall the <b>if-ladder</b> from the last lecture:

<br>

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
<br>
* The <b>if-ladder</b> can get really messy, so pay extra attention to the number and relative positions of <code>if</code> and <code>else</code>
  <br>
* Let's say we have a program that asks the user to make a choice from one to five</li>
  <br>
 
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
<ul>
  <li>There's a more convenient way to write the code above:</li>
</ul>
<br>

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
<ul>
  <li>This is called a <b>switch statement</b></li>
  <br>
  <ul>
    <li>Notice, after <code>switch</code>, there is a set of parentheses containing the name of the integer</li>
    <br>
    <li>After <code>case</code>, there is an integer specific to the 'case'</li>
    <br>
    <li>If there is another integer that satisfies the same condition, write it immediately on the next line</li>
    <br>
    <li><code>break</code> tells the program to ignore everything else that comes afterward <i>inside</i> the switch statement</li>
    <br>
    <li>If the int does not match any of the cases, it will jump to the <code>default:</code> section</li>
    <br>
  </ul>
</ul>
<br>
<ul>
  <li>What happens if you accidentally forgot to include a <b>break</b>?</li>
    <ul>
      <br>
      <li>The program will run the code for subsequent cases until it sees another <code>break</code></li>
    </ul>
</ul>
<br>
<ul>
  <li>Could you use a range of numbers for cases as in <code>case 10-19:</code>?</li>
    <ul>
      <br>
      <li>No, you need to type each case separately
    </ul>
</ul>
<br>
<ul>
  <li>Could you use greater than or less than signs for cases as in <code>case > 100:</code>?</li>
    <ul>
      <br>
      <li>No, you can only assign a certain case to a certain number
    </ul>
</ul>
<br>
<ul>
  <li>Could you use a switch for strings or doubles?</li>
    <ul>
      <br>
      <li>No, you can only use integers
    </ul>
</ul>
<br><br>
<ul>
  <li>Could you use a switch for strings or doubles?</li>
    <ul>
      <br>
      <li>No, you can only use integers
    </ul>
</ul>

* Hi

[back](./)
