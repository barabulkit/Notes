```python
movies = ["Harry Potter", "Hobbit", "WhoAmI"]
print(movies[0]) #[] to access item at index inside brackets, indexes starts at 0
print(movies[1:3]) #return all items from second to the third (will return 3-1, so actually 2 items)
print(movies[1:]) # return all items from second to the last including
print(movies[:1]) # return one item starting from index 0
print(movies[-1]) # return last item in list
movies.append("plastic") #adds item plastic to the end of list
print(movies)
movies.insert(2, 'throne') #insert item to index 2
movies.pop() # remove last item
movies.pop(3) #remove item at index 3
print(movies)
another_movies = ["grinch", "mask"]
movies_summ = movies + another_movies #add another movies content to the end of movies content and puts 
it into movies_summ var
list2d = [[1,2],[3,4],[5,6]] # two dimensional list 2d_list[0][1] will return 2
```
