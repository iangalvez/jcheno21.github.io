## Lecture 4 Notes

<ul>
  <li>Recall the <b>if-ladder</b> from the last lecture:</li>
</ul>

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

 
[back](./)
