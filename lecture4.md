## Lecture 4 Notes
<br>
<ul>
  <li>Recall the <b>if-ladder</b> from the last lecture:</li>
</ul>
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
<ul>
  <li>The <b>if-ladder</b> can get really messy, so pay extra attention to the number and relative positions of <code>if</code> and <code>else</code></li>
  <br>
  <li>Let's say we have a program that asks the user to make a choice from one to five</li>
  <br>
</ul>
 
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

```cpp
int main()
{
  ...
  int choice;
  cin >> choice;
  switch (choice) // Use the keyword 'switch'
  {
    case 1: // Notice the integer that choice is equal to proceeds 'case'
      cout << "Do thing A" << endl;
      break;
    case 2:
    case 4:
      cout << "Do thing B" << endl;
      break;
    case 3:
    case 5:
      cout << "Do thing B" << endl;
      break;
    default:
      cout << "Choice must be 1 through 5." << endl;
      cout << "I'll assume you wanted choice 1" << endl;
      cout << "Do thing A" << endl;
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
    <li><code>break</code> tells the program to ignore everything else that comes afterward in the switch statement</li>
  </ul>
</ul>


[back](./)
