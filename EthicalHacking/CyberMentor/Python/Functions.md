```python
def func(): # its a function without params
    a = 42 # local var, not visible outside of function
    print(a)

def func_with_params(a):
    print(a)

def multiply(x, y):
    return x * y # returns value from function so it can be used somewhere else

func()
func_with_params(30)
function_result = multiply(7, 7)
print(function_result)
```
