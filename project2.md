## Project 2

### Tax Computation Program

```cpp
#include <iostream>
using namespace std;

int main(){
    
// The following section asks for inputs.
    
    // Name
    cout << "Name: ";
    string name;
    getline(cin, name);
    
    // Income
    cout << "Taxable income: ";
    double income;
    cin >> income;
    cin.ignore(10000, '\n');
    
    // Occupation
    cout << "Occupation: ";
    string occupation;
    getline(cin, occupation);
    
    // Number of Children
    cout << "Number of children: ";
    int children;
    cin >> children;
    
// The following are the computations of the program.
    
    double initialAmountTaxed = 0;
    
    // Initial Amount Taxed for Normal People
    // Overrides line 31 if certain conditions are satisfied
    
    if (income >= 0 && income <= 50000)
        initialAmountTaxed = income * 0.04;

    if (income > 50000 && income <= 120000)
        initialAmountTaxed = (50000*0.04) + ((income - 50000)*0.06);
   
    if (income > 120000)
        initialAmountTaxed = (50000*0.04) + (70000*0.06) + ((income - 120000)*0.09);
    
    // Initial Amount Taxed for Scientists and Engineers
    
    if ((occupation == "scientist" || occupation == "engineer") && (income > 50000 && income <= 120000))
        initialAmountTaxed = (50000*0.04) + ((income - 50000)*0.05);
    
    if ((occupation == "scientist" || occupation == "engineer") && (income > 120000))
        initialAmountTaxed = (50000*0.04) + (70000*0.05) + ((income - 120000)*0.09);
    
    // Deductions for Number of Children if Income < $120,000
    
    double intermediateAmountTaxed;
    double finalAmountTaxed;
    
    if (income < 120000)
        intermediateAmountTaxed = initialAmountTaxed - (200 * children);
    
    else
        intermediateAmountTaxed = initialAmountTaxed;
        
    if (intermediateAmountTaxed < 0)
        finalAmountTaxed = 0;
    
    else
        finalAmountTaxed = intermediateAmountTaxed;
    
// The following are outputs of the code
    
    // Sets all subsequent outputs to two decimal places
    cout.setf(ios::fixed);
    cout.precision(2);
    
    // Three hyphens
    cout << "---" << endl;
    
    // Five different possible outputs
    // Used an if-ladder since there shouldn't be multiple lines
    
    if (name == "")
        cout << "You must enter a name" << endl;
    
    else
    {if (income < 0)
        cout << "The taxable income must be nonnegative" << endl;
        
        else
        {if (occupation == "")
            cout << "You must enter an occupation" << endl;
            
            else
            {if (children < 0)
                cout << "The number of children must be nonnegative" << endl;
                
                else
                    cout << name << " would pay $" << finalAmountTaxed << endl;
    
            }}}
}
```

 
[Home](./)
