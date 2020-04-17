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
<ul>
  <li>The <b>if-ladder</b> can get really messy</li>
  <ul>
    <li>Pay extra attention to the number and relative position of <code>if</code> and <code>else</code></li>
  </ul>
</ul>
 
[back](./)
