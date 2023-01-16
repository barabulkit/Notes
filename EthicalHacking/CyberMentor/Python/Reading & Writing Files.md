```python
monthsFile = open('months.txt')

print(monthsFile)
print(monthsFile.mode)
print(monthsFile.readable())
print(monthsFile.readline())
print(monthsFile.read())
monthsFile.seek(0)
print(monthsFile.readlines())
monthsFile.seek(0)

for month in monthsFile:
    print(month.strip())

monthsFile.close()

daysFile = open('days.txt', 'w')
daysFile.write("Monday")
daysFile.close()

daysFile = open('days.txt', 'a')
daysFile.write('Thursday')
daysFile.close()
```
