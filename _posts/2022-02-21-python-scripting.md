---
title: Python Scripting
author:
  name: Team141
  link: https://github.com/Team141
date: 2022-02-18 11:33:00 +0530
categories: [Bash scripting, Linux]
tags: [Bash scripts]
math: true
mermaid: true
pin: false
---

## Code block

---

```python
print ("welcome to Python")

```

    welcome to Python



```python
print("Python indentations")
```

    Python indentations



```python
print("Python indentations")
print("")
print("#######")
```

    Python indentations

    #######



```python
#This is comment, single line
print("$$$$$$$$$$$$$$")
```

    $$$$$$$$$$$$$$



```python
"""This
is a
multi line
comment"""
print("&&&&&&&&&&")
```

    &&&&&&&&&&



```python
'''
This is
a multi line
comment'''
print("$$$$$$$$$$$$")
```

    $$$$$$$$$$$$



```python
Name='python'
print("Name")
print(Name)
print('Name')
```

    Name
    python
    Name



```python
Name=Python
Python='Python'
print("This is a string.")
print('This is a string.')
```

    This is a string.
    This is a string.


Python='Python'
print("This is a",Python)


```python
print("Kumar raj luckynumber is",7)

```

    Kumar raj luckynumber is 7



```python
#Paragraph string
print("""This
is
a
multi line
string print""")
```

    This
    is
    a
    multi line
    string print



```python
a = 'alpha'
b = "beta"
c = """theta"""

print("a for",a,"\nb for",b,"\nc for",c)
```

    a for alpha
    b for beta
    c for theta



```python
print(type(a))
```

    <class 'str'>



```python
#Numbers
#Integer

x = 12
y = 6.7

print(x,y)
```

    12 6.7



```python
#List, collection of multi datatypes, enclosed in []. This
# datatypes can be changeable(MUTABLE)

list1 = [a, b, c, "Devops", 89, 90.245]


print(list1)
```

    ['alpha', 'beta', 'theta', 'Devops', 89, 90.245]



```python
#Tuple, collection of multi datatypes, enclosed in {}. This
# datatypes can be changeable(IMMUTABLE)

tuple1 = {a, b, c, "Devops", 89, 90.245}

print(tuple1)
```

    {'theta', 'Devops', 'beta', 89, 90.245, 'alpha'}



```python
#Dictionary, collection of elements in pair(key:value), enclosed inside {}

my_dictionary = {"Name":"Kumar Raj","Age":21,"Weight":54,"Hobbies":["Reading","Listening to Music"]}


print(my_dictionary)
```

    {'Name': 'Kumar Raj', 'Age': 21, 'Weight': 54, 'Hobbies': ['Reading', 'Listening to Music']}



```python
###SLICING

message = "Virus new variant is deltacron"

print(message)
```

    Virus new variant is deltacron



```python
print(message[0])
print(message[3])
print(message[-4])
print(message[-1+1])
```

    V
    u
    c
    V



```python
#string slicing
print(message[6:10])
```

    new



```python
print(message[10:17])
```

    variant



```python
print(message[-9:])
```

    deltacron



```python
print(message[:5])
```

    Virus



```python
#List Slicing

animals=["snake", "Honeybadger", "Trex", "Leopard", "Cheetah", "Elephant", "crocodile"]
```


```python
print(animals)
```

    ['snake', 'Honeybadger', 'Trex', 'Leopard', 'Cheetah', 'Elephant', 'crocodile']



```python
print(animals[1])
print(animals[2:5])
print(animals[:4])
print(animals[-3:])
```

    Honeybadger
    ['Trex', 'Leopard', 'Cheetah']
    ['snake', 'Honeybadger', 'Trex', 'Leopard']
    ['Cheetah', 'Elephant', 'crocodile']



```python
print(animals[2:5])
```

    ['Trex', 'Leopard', 'Cheetah']



```python
print(animals[2:5][-2])
```

    Leopard



```python
print(animals[2:5][-2][:3])
```

    Leo



```python
print(animals[2:5][-2][:3][-1])
```

    o



```python
#Slicing Dictionary

my_dictionary= {"Name":"Imran", "Age": 24, "Weight": 73.5, "Hobbies":["Dance", "Boxing", "Swimming"]}
print(my_dictionary)
```

    {'Name': 'Imran', 'Age': 24, 'Weight': 73.5, 'Hobbies': ['Dance', 'Boxing', 'Swimming']}



```python
print(my_dictionary["Name"])
```

    Imran



```python
print(my_dictionary["Hobbies"][-1])
```

    Swimming



```python
print(my_dictionary["Hobbies"][-1][4:])
```

    ming



```python

```
