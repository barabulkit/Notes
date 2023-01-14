```python
str = "some string"
print(str.split()) #splits by delimeter, default is space, will return list ['some', 'string']
str_splitted = str.split()
str_joined = ' '.join(str_splitted) # joins string using invoking object as a delimeter
print(str_joined)
str = "         spaces          "
print(str.strip()) # removes all delimiter chars from start and end of the string

print("A" in "Apple") #checks if letter exist in the string, its case-sensitive

print("the number is {}".format(42)) # string formatting
print("the number is %d" % 42) #another way of string formatting
print(f"the str is {str}") #string formatting with variable usage
```