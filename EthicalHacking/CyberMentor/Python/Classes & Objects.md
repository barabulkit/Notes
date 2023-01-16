employees.py file
```python
class Employees:
    def __init__(self, name, department, role, salary, years_employed):
        self.name = name
        self.department = department
        self.role = role
        self.salary = salary
        self.years_employed = years_employed
        
    def eligible_for_retirment(self):
        if self.years_employed >= 20:
            return True
        else:
            return False
```
main.py file
```python
from employees import Employees # employees is name of another py file in the same folder

e1 = Employees("Bob", "Sales", "Director of Sales", 100000, 20)
e2 = Employees("Linda", "Executive", "CIO", 150000, 10)

print(e1.name)
print(e2.eligible_for_retirment())
```
