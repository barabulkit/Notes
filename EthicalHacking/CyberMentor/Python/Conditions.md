```python
greater_than = 7 > 5
less_than = 5 < 7
greater_than_equal_to = 7 >= 7
less_than_equal_to = 7 <= 7

test_and = (7 > 5) and (5 < 7) #and will true if both are true
test_or = (5 > 7) or (4 < 7) #or will be false if both are false

def drink(money):
    if money >= 2:
        return "you bought a drink"
    else:
        return "you can not but a drink"

def alcohol(age, money):
    if(age >= 18) and (money >= 5):
        return "you bought an alcohol"
    elif(age >= 18) and (money < 5):
        return "not enough money"
    elif(age < 18) and (money >= 5):
        return "you are too young"
    else:
        return "what are you even doing here?"

```
