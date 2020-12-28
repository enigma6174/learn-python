# Introduction To Python Programming : Part 2 
<hr />

In this section, we will be looking at the most popular in-built data structures provided by Python and how we can use them to solve all our programming challenges, build applications, work on any projects etc

## Topics Covered
<hr />

- Lists
    - Basics Of Lists
    - List Manipulations
    - List Comprehensions
    - Advanced List Operations
    
- Dictionaries

    - Basics Of Dictionaries
    - Dictionary Manipulations

- Sets & Tuples

    - Basics Of Sets And Tuples
    - Manipulating Sets And Tuples
    - Differences Between Sets And Tuples
    
- Extras

    - zip() function
    - enumerate() function
    - map() function
    - Lambda function in Python

## Lists
<hr />

### Basics Of List

- Defining A List
- Accessing The Elements Of List
- Length Of The List

#### Defining A List


```python
# Define different types of list
numList = [1, 2, 3, 10, -89, 4]
strList = ["hello", "world", "welcome", "to", "Python", "Programming"]
frcList = [6.131, 2.3141, 0.0001, 23411e-5, 2.6771e10, -451e-4]
mixList = [12, 1.122, 4.5231e2, "hello", "world", True]

dumbList_1 = [34, 4.34e-2, True, "hello", "magical world", -91]
dumbList_2 = ["good", "boy", 0.034115e3, -45, False, 'a']

# Print the list and their types
print(f"number list\n{numList}\n")
print(f"string list\n{strList}\n")
print(f"fraction list\n{frcList}\n")
print(f"mixed elements list\n{mixList}\n")
```

    number list
    [1, 2, 3, 10, -89, 4]
    
    string list
    ['hello', 'world', 'welcome', 'to', 'Python', 'Programming']
    
    fraction list
    [6.131, 2.3141, 0.0001, 0.23411, 26771000000.0, -0.0451]
    
    mixed elements list
    [12, 1.122, 452.31, 'hello', 'world', True]
    


#### Accessing The Elements Of List


```python
# Accessing the individual list elements from the start
print(f"first element of numList[] is {numList[0]}")
print(f"third element of numList[] is {numList[2]}")

print()

# Acessing the individual list elements from the end
print(f"first element of strList[] from end is '{strList[-1]}'")
print(f"second last element of strList[] from end is '{strList[-2]}'")

print()

# Accessing the beginning elements of the list from the end
print(f"last element of strList[] from end is '{strList[-6]}'")
print(f"second last element of strList[] from end is '{strList[-5]}'")

print()

# Accessing the elements of the list based on mathematical expressions
print(f"n-th element of frcList[] is {frcList[]}")
```

    first element of numList[] is 1
    third element of numList[] is 3
    
    first element of strList[] from end is 'Programming'
    second last element of strList[] from end is 'Python'
    
    last element of strList[] from end is 'hello'
    second last element of strList[] from end is 'world'



```python
# Iterating over the list using for loop - last index exclusive
print("elements of frcList[] (last index exclusive) : ")
for i in range(0, 5):
    print(frcList[i])

print()

# Iterating over the list using for loop - last index inclusive
print("elements of frcList[] (last index inclusive) : ")
for i in range(0, 6):
    print(frcList[i])
    
print()

# Alternative approach to iterating over the list using for loop
print("elements of frcList[] : ")
for i in frcList:
    print(i)

print()

# Printing the elements at even positions in frcList[]
print("elements at even indexes in frcList[] : ")
for i in range(0, 6):
    if (i % 2 == 0):
        print(frcList[i])
```

    elements of frcList[] (last index exclusive) : 
    6.131
    2.3141
    0.0001
    0.23411
    26771000000.0
    
    elements of frcList[] (last index inclusive) : 
    6.131
    2.3141
    0.0001
    0.23411
    26771000000.0
    -0.0451
    
    elements of frcList[] : 
    6.131
    2.3141
    0.0001
    0.23411
    26771000000.0
    -0.0451
    
    elements at even indexes in frcList[] : 
    6.131
    0.0001
    26771000000.0



```python
# Iterating over the list from start to end using while loop
print("iterating over mixList[] using while loop (start -> end) : ")
i = 0
while (i < 6):
    print(frcList[i])
    i += 1
    
print()

# Iterating over the list from end to start using while loop
print("iterating over mixList[] using while loop (end -> start) : ")
i = 5
while (i >= 0):
    print(frcList[i])
    i -= 1
    
print()
```

    iterating over mixList[] using while loop (start -> end) : 
    6.131
    2.3141
    0.0001
    0.23411
    26771000000.0
    -0.0451
    
    iterating over mixList[] using while loop (end -> start) : 
    -0.0451
    26771000000.0
    0.23411
    0.0001
    2.3141
    6.131
    


data types of list elements vs data type of list


```python
# Data types of list
print(f"number list data type : {type(numList)}")
print(f"string list data type : {type(strList)}")
print(f"fraction list data type : {type(frcList)}")
print(f"mixed elements list data type : {type(mixList)}")

print()

# Data types of elements inside list
print(f"numList[0] data type : {type(numList[0])}")
print(f"strList[-1] data type : {type(strList[-1])}")
print(f"frcList[3] data type : {type(frcList[3])}")
print(f"mixList[0] data type : {type(mixList[0])}")
print(f"mixList[-1] data type : {type(mixList[-1])}")
print(f"mixList[-2] data type : {type(mixList[-2])}")
```

    number list data type : <class 'list'>
    string list data type : <class 'list'>
    fraction list data type : <class 'list'>
    mixed elements list data type : <class 'list'>
    
    numList[0] data type : <class 'int'>
    strList[-1] data type : <class 'str'>
    frcList[3] data type : <class 'float'>
    mixList[0] data type : <class 'int'>
    mixList[-1] data type : <class 'bool'>
    mixList[-2] data type : <class 'str'>


#### Length Of The List


```python
# Print the length of the list
print(f"length of numList : {len(numList)}")
print(f"length of mixList : {len(mixList)}")

print()

# Accessing elements of the list using the length 
print(f"strList[-1] : {mixList[len(strList) - 1]}")
print(f"mixList[-2] : {mixList[len(mixList) - 2]}")

print()

# Iterating over the list using the length (for-loop)
print("elements of frcList[] (start -> end) : ")
for i in range(0, len(frcList)): 
    print(frcList[i])

print() 

# Iterating over the list using the length (while-loop)
print("elements of mixList (end -> start) : ")
i = len(mixList) - 1
while i >= 0:
    print(mixList[i])
    i -= 1
```

    length of numList : 6
    length of mixList : 6
    
    strList[-1] : True
    mixList[-2] : world
    
    elements of frcList[] (start -> end) : 
    6.131
    2.3141
    0.0001
    0.23411
    26771000000.0
    -0.0451
    
    elements of mixList (end -> start) : 
    True
    world
    hello
    452.31
    1.122
    12


### List Manipulations

- Modifying The List Items
- Adding Items To The List
- Removing Items From The List
- More Operations On Lists
    - clear()
    - reverse()
    - sort()
    - count()
- Slicing A List

#### Modifying The List Items


```python
print(f"nunmList[]\n{numList}\n")
print(f"strList[]\n{strList}\n")

# Modifying the first entry of numList[] and last entry of strList[]
numList[0] = 234
strList[-1] = "modified"

print(f"numList[]\n{numList}\n")
print(f"strList[]\n{strList}\n")


print(f"numList[] (current list)\n{numList}\n")

# Updating the list value by mathematical expression
numList[-2] = (numList[0] * 2) - 345 + numList[2]

print(f"numList[] (modified 2nd last index)\n{numList}\n")


print(f"strList[] (current list)\n{strList}\n")

# Updating the list value by concatenation
strList[-1] = strList[-1] + ' ' + strList[0] + '!'

print(f"strList[] (modified last index)\n{strList}\n")


print(f"dumbList[]\n{dumbList_2}\n")

# Setting elements of dumbList_2 to None
dumbList_2 = None
print(f"dumbList[] TYPE : {type(dumbList_2)}\n{dumbList_2}\n")
```

    nunmList[]
    [1, 2, 3, 10, -89, 4]
    
    strList[]
    ['hello', 'world', 'welcome', 'to', 'Python', 'Programming']
    
    numList[]
    [234, 2, 3, 10, -89, 4]
    
    strList[]
    ['hello', 'world', 'welcome', 'to', 'Python', 'modified']
    
    numList[] (current list)
    [234, 2, 3, 10, -89, 4]
    
    numList[] (modified 2nd last index)
    [234, 2, 3, 10, 126, 4]
    
    strList[] (current list)
    ['hello', 'world', 'welcome', 'to', 'Python', 'modified']
    
    strList[] (modified last index)
    ['hello', 'world', 'welcome', 'to', 'Python', 'modified hello!']
    
    dumbList[]
    ['good', 'boy', 34.115, -45, False, 'a']
    
    dumbList[] TYPE : <class 'NoneType'>
    None
    


#### Adding Items To The List

Adding items to the end of the list - _append()_


```python
print("INPUT")
print("-" * 5)
print(f"numList[]\n{numList}\n")
print(f"strList[]\n{strList}\n")

# Adding an item to the end of the list (append)
numList.append(999)
strList.append("last")

print("OUTPUT")
print("-" * 6)
print(f"numList[]\n{numList}\n")
print(f"strList[]\n{strList}\n")
```

    INPUT
    -----
    numList[]
    [234, 2, 3, 10, 126, 4]
    
    strList[]
    ['hello', 'world', 'welcome', 'to', 'Python', 'modified hello!']
    
    OUTPUT
    ------
    numList[]
    [234, 2, 3, 10, 126, 4, 999]
    
    strList[]
    ['hello', 'world', 'welcome', 'to', 'Python', 'modified hello!', 'last']
    


Adding element **x** at position **i** in the list - _insert(i,x)_


```python
print("INPUT")
print("-" * 5)
print(f"numList[]\n{numList}\n")
print(f"strList[]\n{strList}\n")

# Adding item to list at index i=1 (insertion at index 0)
numList.insert(1, -111)
strList.insert(1, "first")

print("OUTPUT")
print("-" * 6)
print(f"numList[]\n{numList}\n")
print(f"strList[]\n{strList}\n")
```

    INPUT
    -----
    numList[]
    [234, 2, 3, 10, 126, 4, 999]
    
    strList[]
    ['hello', 'world', 'welcome', 'to', 'Python', 'modified hello!', 'last']
    
    OUTPUT
    ------
    numList[]
    [234, -111, 2, 3, 10, 126, 4, 999]
    
    strList[]
    ['hello', 'first', 'world', 'welcome', 'to', 'Python', 'modified hello!', 'last']
    



```python
print("INPUT")
print("-" * 5)
print(f"numList[]\n{numList}\n")
print(f"strList[]\n{strList}\n")

# Adding item to list at index k=4 (insertion at index 3)
numList.insert(4, 444)
strList.insert(4, "foursquare")

print("OUTPUT")
print("-" * 6)
print(f"numList[]\n{numList}\n")
print(f"strList[]\n{strList}\n")
```

    INPUT
    -----
    numList[]
    [234, -111, 2, 3, 10, 126, 4, 999]
    
    strList[]
    ['hello', 'first', 'world', 'welcome', 'to', 'Python', 'modified hello!', 'last']
    
    OUTPUT
    ------
    numList[]
    [234, -111, 2, 3, 444, 10, 126, 4, 999]
    
    strList[]
    ['hello', 'first', 'world', 'welcome', 'foursquare', 'to', 'Python', 'modified hello!', 'last']
    



```python
print("INPUT")
print("-" * 5)
print(f"numList[]\n{numList}\n")
print(f"strList[]\n{strList}\n")

# Adding item to second last position
numList.insert(-1, -2)
strList.insert(-1, "secondlast")

print("OUTPUT")
print("-" * 6)
print(f"numList[]\n{numList}\n")
print(f"strList[]\n{strList}\n")
```

    INPUT
    -----
    numList[]
    [234, -111, 2, 3, 444, 10, 126, 4, 999]
    
    strList[]
    ['hello', 'first', 'world', 'welcome', 'foursquare', 'to', 'Python', 'modified hello!', 'last']
    
    OUTPUT
    ------
    numList[]
    [234, -111, 2, 3, 444, 10, 126, 4, -2, 999]
    
    strList[]
    ['hello', 'first', 'world', 'welcome', 'foursquare', 'to', 'Python', 'modified hello!', 'secondlast', 'last']
    



```python
print("INPUT")
print("-" * 5)
print(f"numList[]\n{numList}\n")
print(f"strList[]\n{strList}\n")

# Adding item to last position by insert()
numList.insert(len(numList), 666)
strList.insert(len(strList), "#FFF")

print("OUTPUT")
print("-" * 6)
print(f"numList[]\n{numList}\n")
print(f"strList[]\n{strList}\n")
```

    INPUT
    -----
    numList[]
    [234, -111, 2, 3, 444, 10, 126, 4, -2, 999]
    
    strList[]
    ['hello', 'first', 'world', 'welcome', 'foursquare', 'to', 'Python', 'modified hello!', 'secondlast', 'last']
    
    OUTPUT
    ------
    numList[]
    [234, -111, 2, 3, 444, 10, 126, 4, -2, 999, 666]
    
    strList[]
    ['hello', 'first', 'world', 'welcome', 'foursquare', 'to', 'Python', 'modified hello!', 'secondlast', 'last', '#FFF']
    


An interesting outcome


```python
print(len(numList))
print(numList)
```

    11
    [234, -111, 2, 3, 444, 10, 126, 4, -2, 999, 666]



```python
# Insert at a new last index
numList.insert(11, 101)
print(numList)
```

    [234, -111, 2, 3, 444, 10, 126, 4, -2, 999, 666, 101]



```python
# Insert at another new last index
numList.insert(15, 1500)
print(numList)
```

    [234, -111, 2, 3, 444, 10, 126, 4, -2, 999, 666, 101, 1500]



```python
print(len(numList))
print(numList)
```

    13
    [234, -111, 2, 3, 444, 10, 126, 4, -2, 999, 666, 101, 1500]



```python
# Insert at start index
numList.insert(-13, -1300)
print(numList)
```

    [-1300, 234, -111, 2, 3, 444, 10, 126, 4, -2, 999, 666, 101, 1500]



```python
# Insert at new start index
numList.insert(-18, -1800)
print(numList)
```

    [-1800, -1300, 234, -111, 2, 3, 444, 10, 126, 4, -2, 999, 666, 101, 1500]



```python
print(len(numList))
print(numList)
```

    15
    [-1800, -1300, 234, -111, 2, 3, 444, 10, 126, 4, -2, 999, 666, 101, 1500]


#### Removing Items From The List

Removing item **x** from the list _remove(x)_


```python
print(f"strList[]\n{strList}\n")

# Remove the item "hello" from the list
strList.remove("hello")
print(f"strList[]\n{strList}\n")

# Remove the item "modified hello!" from the list
strList.remove("modified hello!")
print(f"strList[]\n{strList}\n")
```

    strList[]
    ['hello', 'first', 'world', 'welcome', 'foursquare', 'to', 'Python', 'modified hello!', 'secondlast', 'last', '#FFF']
    
    strList[]
    ['first', 'world', 'welcome', 'foursquare', 'to', 'Python', 'modified hello!', 'secondlast', 'last', '#FFF']
    
    strList[]
    ['first', 'world', 'welcome', 'foursquare', 'to', 'Python', 'secondlast', 'last', '#FFF']
    


Removing multiple items from the list


```python
print(f"strList[]\n{strList}\n")
```

    strList[]
    ['first', 'world', 'welcome', 'foursquare', 'to', 'Python', 'secondlast', 'last', '#FFF']
    


approach#1


```python
strList.remove("first", "last", "foursquare")
print(f"strList[]\n{strList}\n")
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-85-7cdae9755d75> in <module>
    ----> 1 strList.remove("first", "last", "foursquare")
          2 print(f"strList[]\n{strList}\n")


    TypeError: remove() takes exactly one argument (3 given)


approach#2


```python
strList.remove(["first", "second", "foursquare"])
print(f"strList[]\n{strList}\n")
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-86-737bd315f7c5> in <module>
    ----> 1 strList.remove(["first", "second", "foursquare"])
          2 print(f"strList[]\n{strList}\n")


    ValueError: list.remove(x): x not in list


correct approach


```python
# Correct approach to remove multiple items from the list
buffer = ["first", "last", "foursquare"]
for b in buffer:
    strList.remove(b)
    
print(f"strList[]\n{strList}\n")
```

    strList[]
    ['world', 'welcome', 'to', 'Python', 'secondlast', '#FFF']
    


Popping an element from the list at index **i** and returning the element - _pop(i)_


```python
print(f"numList[]\n{numList}\n")
```

    numList[]
    [-1800, -1300, 234, -111, 2, 3, 444, 10, 126, 4, -2, 999, 666, 101, 1500]
    



```python
# Pop the element at the first and last index
i = numList.pop(0)
j = numList.pop(-1)

print(f"pop(0) is {i} and pop(-1) is {j}")
print(f"numList[]\n{numList}\n")
```

    pop(0) is -1800 and pop(-1) is 1500
    numList[]
    [-1300, 234, -111, 2, 3, 444, 10, 126, 4, -2, 999, 666, 101]
    



```python
print(f"numList[]\n{numList}\n")

# Pop the n-th element from the list (n=6 ie. index 5)
k = numList.pop(5)
print(f"pop(5) is {k}")
print(f"numList[]\n{numList}\n")
```

    numList[]
    [-1300, 234, -111, 2, 3, 444, 10, 126, 4, -2, 999, 666, 101]
    
    pop(5) is 444
    numList[]
    [-1300, 234, -111, 2, 3, 10, 126, 4, -2, 999, 666, 101]
    


Popping multiple items from list


```python
print(f"numList[]\n{numList}\n")
```

    numList[]
    [-1300, 234, -111, 2, 3, 10, 126, 4, -2, 999, 666, 101]
    


approach#1


```python
# Pop the first, last and second last elements from the list
i, j, k = numList.pop(0, -1, -2)

print()
print(f"pop(0) : {i}, pop(-1) : {j}, pop(-2) : {k}")
print(f"numList[]\n{numList}\n")
```

    numList[]
    [-1300, 234, -111, 2, 3, 10, 126, 4, -2, 999, 666, 101]
    



    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-92-a31a38240c4b> in <module>
          2 
          3 # Pop the first, last and second last elements from the list
    ----> 4 i, j, k = numList.pop(0, -1, -2)
          5 
          6 print()


    TypeError: pop() takes at most 1 argument (3 given)


approach#2


```python
print(f"numList[]\n{numList}\n")

# Pop the first, last and second last elements from the list
i, j, k = numList.pop([0, -1, -2])

print()
print(f"pop(0) : {i}, pop(-1) : {j}, pop(-2) : {k}")
print(f"numList[]\n{numList}\n")
```

    numList[]
    [-1300, 234, -111, 2, 3, 10, 126, 4, -2, 999, 666, 101]
    



    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-93-12635ed60224> in <module>
          2 
          3 # Pop the first, last and second last elements from the list
    ----> 4 i, j, k = numList.pop([0, -1, -2])
          5 
          6 print()


    TypeError: 'list' object cannot be interpreted as an integer


approach#3


```python
# Correct approach to popping multiple items from the list
buffer = [0, -1, -2]
for b in buffer:
    k = numList.pop(b)
    print(f"pop({b}) : {k}")
    
print()
print(f"numList[]\n{numList}\n")
```

    pop(0) : -1300
    pop(-1) : 101
    pop(-2) : 999
    
    numList[]
    [234, -111, 2, 3, 10, 126, 4, -2, 666]
    



```python
print(f"numList[]\n{numList}\n")

# If index is not specified, pop(i) removes the last element
k = numList.pop()

print(f"pop() : {k}")
print(f"numList[]\n{numList}\n")
```

    numList[]
    [234, -111, 2, 3, 10, 126, 4, -2, 666]
    
    
    pop() : 666
    numList[]
    [234, -111, 2, 3, 10, 126, 4, -2]
    



```python
print(f"numList[]\n{numList}\n")

# If index is out of range, it will throw an error
k = numList.pop(len(numList))

print(f"pop(len(numList)) : {k}")
print(f"numList[]\n{numList}\n")
```

    numList[]
    [234, -111, 2, 3, 10, 126, 4, -2]
    



    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    <ipython-input-97-c1b44e00a830> in <module>
          2 
          3 # If index is not specified, pop(i) removes the last element
    ----> 4 k = numList.pop(len(numList))
          5 
          6 print(f"pop(len(numList)) : {k}")


    IndexError: pop index out of range


#### clear()


```python
print(f"frcList[] MEM_ADDR : {id(frcList)}\n{frcList}\n")
print(f"mixList[] MEM_ADDR : {id(mixList)}\n{mixList}\n")
```

    frcList[] MEM_ADDR : 140489929050304
    [6.131, 2.3141, 0.0001, 0.23411, 26771000000.0, -0.0451]
    
    mixList[] MEM_ADDR : 140489929050224
    [12, 1.122, 452.31, 'hello', 'world', True]
    



```python
# Clear the list using clear()
frcList.clear()

# Clear the list by assigning a new empty list
mixList = []

print(f"frcList[] MEM_ADDR : {id(frcList)}\n{frcList}\n")
print(f"mixList[] MEM_ADDR : {id(mixList)}\n{mixList}\n")
```

    frcList[] MEM_ADDR : 140489929050304
    []
    
    mixList[] MEM_ADDR : 140489929071744
    []
    


#### reverse()


```python
tempList = [34, 4.34e-2, True, "hello", "magical world", -91, False, None, 1]

print(f"tempList[] MEM_ADDR : {id(tempList)}\n{tempList}\n")

# Reverse the list in-place (memory address does not change)
tempList.reverse()

# List is changed permanently
print(f"tempList[] MEM_ADDR : {id(tempList)}\n{tempList}\n")
```

    tempList[] MEM_ADDR : 140489929964992
    [34, 0.0434, True, 'hello', 'magical world', -91, False, None, 1]
    
    tempList[] MEM_ADDR : 140489929964992
    [1, None, False, -91, 'magical world', 'hello', True, 0.0434, 34]
    


#### sort()


```python
tempList = [89, -90, 231, -1000, 0, 55, 89, 231, 7, 13, -90, 85, 13, 5, -90, -90, 12, 56, 7, 8, 101, -90, 85, 2, 0]
print(f"tempList[]\n{tempList}\n")
```

    tempList[]
    [89, -90, 231, -1000, 0, 55, 89, 231, 7, 13, -90, 85, 13, 5, -90, -90, 12, 56, 7, 8, 101, -90, 85, 2, 0]
    



```python
# Sort the list in-place in ascending order (default)
tempList.sort()
print(f"tempList[] SORTED (ascending)\n{tempList}\n")

# Sort the list in-place in descending order
tempList.sort(reverse=True)
print(f"tempList[] SORTED (descending)\n{tempList}\n")
```

    tempList[] SORTED (ascending)
    [-1000, -90, -90, -90, -90, -90, 0, 0, 2, 5, 7, 7, 8, 12, 13, 13, 55, 56, 85, 85, 89, 89, 101, 231, 231]
    
    tempList[] SORTED (descending)
    [231, 231, 101, 89, 89, 85, 85, 56, 55, 13, 13, 12, 8, 7, 7, 5, 2, 0, 0, -90, -90, -90, -90, -90, -1000]
    


#### count(x)


```python
tempList = [89, -90, 231, -1000, 0, 55, 89, 231, 7, 13, -90, 85, 13, 5, -90, -90, 12, 56, 7, 8, 101, -90, 85, 2, 0]
print(f"tempList[]\n{tempList}\n")
```

    tempList[]
    [89, -90, 231, -1000, 0, 55, 89, 231, 7, 13, -90, 85, 13, 5, -90, -90, 12, 56, 7, 8, 101, -90, 85, 2, 0]
    



```python
# Count the number of times 85 appears in the list
j = tempList.count(85)
print(f"85 appears in tempList[] {j} times")

print()

# Count the number of times -90, 89, 5 appear in the list
keys = [-90, 89, 5]
for key in keys:
    print(f"{key} appears in tempList[] {tempList.count(key)} times")
```

    85 appears in tempList[] 2 times
    
    -90 appears in tempList[] 5 times
    89 appears in tempList[] 2 times
    5 appears in tempList[] 1 times


#### Slicing A List


```python
tempList = [89, -90, 231, -1000, 0, 55, 89, 231, 7, 13, -90, 85, 13, 5, -90, -90, 12, 56, 7, 8, 101, -90, 85, 2, 0]
print(f"tempList[]\n{tempList}\n")
```

    tempList[]
    [89, -90, 231, -1000, 0, 55, 89, 231, 7, 13, -90, 85, 13, 5, -90, -90, 12, 56, 7, 8, 101, -90, 85, 2, 0]
    



```python
# Slice the list from index [0,4)
print(tempList[0:4])
```

    [89, -90, 231, -1000]



```python
# Slice the list from index [3, 8]
print(tempList[3:9])
```

    [-1000, 0, 55, 89, 231, 7]



```python
# Slice the list from index [0, 25] in steps of 3
print(tempList[0:25:3])
```

    [89, -1000, 89, 13, 13, -90, 7, -90, 0]



```python
# Slice the list from index [4, 17) in steps of 5
print(tempList[4:17:5])
```

    [0, 13, -90]



```python
# Slice the list from end starting index
print(tempList[-1:-10])
```

    []


### List Comprehensions


```python

```
