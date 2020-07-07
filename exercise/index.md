# Basics of Functions in Python

### 1. Functions & Their Parts


```python
def sub1(a,b):
    print(b,"-",a,"=",b-a)
```

1. **Function Name:** ```sub1```
2. **Agruments Required:** ```a``` & ```b``` (2)
3. **Number of Statements _(in body)_ :** one (1)
4. **Returned Value:** _none_
5. **Objective:** it takes 2 arguments and **substracts first** one **from the second** argument

---


```python
def cube2(x):
    x*x*x # a ')' at the end seems to ba a printing mistake
    return x*x*x-x
```

1. **Function Name:** ```cube2```
2. **Agruments Required:** ```x``` (1)
3. **Number of Statements _(in body)_ :** two
4. **Returned Value:** result after subtracting a number from its cube
5. **Working:** In first statement of the definition, the passed argument/number is multiplied **thrice**. In last statement, the same number is again multiplied thrice and then the it's also subtracted from the resulting product i.e. cube. This final outcome is returned! Here first statement is not very significant.

---


```python
def cube1(x):
    return x*x*x
```

1. **Function Name:** ```cube1```
2. **Agruments Required:** ```x``` (1)
3. **Number of Statements _(in body)_ :** one
4. **Returned Value:** cube of a number
5. **Objective:** finds the **cube** of a number i.e. passed as argument, by **multiplying it thrice** with itself

---


```python
def greeting():
    print("Welcome to Python")
```

1. **Function Name:** ```greeting```
2. **Agruments Required:** none
3. **Number of Statements _(in body)_ :** 1
4. **Returned Value:** none
5. **Objective:** prints a **welcome messege**

---
<br /><br />

### 2. Function Call Statements for Above (4) Definitions


```python
## variables, to use

x,y = 3,4
num = 5
```

#### for sub1()


```python
sub1(x,y) # (h)
```

    4 - 3 = 1



```python
sub1(5,3) # (k)
```

    3 - 5 = -2


#### for cube1()


```python
cube1(x) # (i)
```




    27



#### for cube2()


```python
cube2(num) # (l)
```




    120



#### for greeting()


```python
greeting() # (g)
```

    Welcome to Python


---
<br /><br />

### 3. Few Functions


```python
## To return the absolute value for given number

def absolute(num):
    if num < 0:
        num *= -1
    return num
```


```python
# using user defined function
print("|6|  =  ",absolute(6))  # 6
print("|-3| =  ",absolute(-3)) # 3
```

    |6|  =   6
    |-3| =   3



```python
# using inbuilt function   abs()
print("|6|  =  ",abs(6))  # 6
print("|-3| =  ",abs(-3)) # 3
```

    |6|  =   6
    |-3| =   3


---


```python
## check for even / odd number

def chkOdd(num):
    if num%2 == 0:
        print(num, "is Even")
    else:        
        print(num, "is Odd")
```


```python
chkOdd(2)
chkOdd(3)
```

    2 is Even
    3 is Odd


---
<br /><br /><br />

# Modules and More about the Functions

## Modules in Python

**Modules** are just the python programs including various _functions_, _classes_ and many other kinda _definations_. <br />

Alone, they don't play any majour role. But, the modules are necessary when we wish to use the _functions_ or any other defination decleared in it. Inthis way, a python module provides a **modularity**. <br /><br />

A python module as also saved as a normal python program i.e. with the extention ``` .py ``` and are imported using ``` import ``` keyword. <br /><br />

the codes/modules present in current directory can be found [here](https://github.com/ravi-prakash1907/Computer-Science-with-Python/tree/master/exercise)

<br /><br />


### Importing from same dir.

### A Python Mdule to Pint a Wlcome Mssage

<br /> ASSUMING FOLLOWING BE THE MODULE ```hello.py```, PLACED IN THE CURRENT DIRECTORY <br />

```

def greet():
    print("Hey there!! Welcome to the Python Modules!")
    
```

<br /><br />


```python
# importing the module
import hello as greetings
```


```python
# calling the function from module
greetings.greet()
```

    Hey there!! Welcome to the Python Modules!


<br /><br />


### Importing from external/another dir.


```python
import sys
sys.path.append('../dependancies/modules/')
```


```python
import welcome
welcome.greeting()
```

    Hey there!! Welcome to the Python Modules!



```python
welcome.name = welcome.setName()
welcome.msg(welcome.name)
```

    Hello World!!



```python
welcome.name = welcome.setName("Ravi")
welcome.msg(welcome.name)
```

    Hello Ravi!!

_This module can be found [here](https://github.com/ravi-prakash1907/Computer-Science-with-Python/blob/master/dependancies/modules/welcome.py)_

---
<br /><br />

# Exercise

### 1. Module to find **sum** & **product**


```python
import basicMath as m
```


```python
print("2 + 3 = ",m.sum(2,3))
```

    2 + 3 =  5



```python
print("2 X 3 = ",m.product(2,3))
```

    2 X 3 =  6


<br /><br />

### 2. Python function to identify a leap year


```python
def isLeap(year):
    flag = False
    if year%100 == 0 and year%400 == 0:
        flag = True
    elif year%100 != 0 and year%4 == 0:
        flag = True

    return flag
```


```python
if(isLeap(2020)):
    print("2020 is a leap year!")
else:
    print("2020 is NOT a leap year!")
```

    2020 is a leap year!



```python
## True = Leap year  |   False = NOT Leap year

print(isLeap(1992))
print(isLeap(2000))
print(isLeap(1900))
print(isLeap(2100))
```

    True
    True
    False
    False


<br /><br />

### 3. Local VS Global variables in python


```python
# if there is only a Global variable with a name, 
    # it's value is used everywhere in the module/program

name = "Myname"

def caller():
    print("Hey",name, "!!")
    
caller()
```

    Hey Myname !!



```python
# if there is only a Local variable with a name, 
    # it's value is used everywhere wuthin that particular function / class

def caller():
    name = "Myname"
    print("Hey",name, "!!")
    
caller()
```

    Hey Myname !!



```python
# if there are 2 or more variable with same name, (including Global and Local(s), both)
    # keyword 'global' is used to call the global variable

name = "My name"

def caller():
    global name
    #name = "Myname"  # this would change the global variable's value
    print(name," is not 'Myname'!!")
    
caller()
```

    My name  is not 'Myname'!!


<br /><br />

### 4. Module to find pow(x,n)


```python
import power
```


```python
power.pow(2, 10)
```




    1024



<br /><br />

### 5. Create roll_D(noOfSides, noOfDice) and generate random roll values


```python
# since default arguments can only come after defaults, 
# making both the arguments default in order to maintain the order

import random as rand

def roll_D(noOfSides = 6, noOfDice = 1):
    roll = 1
    while roll <= noOfDice:
        rand.randint(1,noOfSides)
        print(li[1])
        roll += 1
    print("That's all")
```

#### Checking for given condition i.e. (6,3)


```python
roll_D(6,3) # 3 dice with 6 faces, each
```

    4
    4
    4
    That's all


<br /><br />

#### Some othe examples


```python
roll_D() # one die with 6 faces
```

    5
    That's all



```python
roll_D(8) # one die with 8 faces
```

    7
    That's all



```python
roll_D(noOfDice = 2) # 2 dice with 6 faces, each
```

    1
    6
    That's all



```python
roll_D(7,3) # 3 dice with 7 faces, each
```

    7
    7
    5
    That's all


<br /><br />

### 6. Prime / Non-Prime Function


```python
def isPrime(num):
    if num == 2 or num == 3:
        flag = True
    elif num%2 != 0:
        for i in range(3, int(num/2)):
            if num%i != 0:
                flag = True
                continue
            else:
                flag = False
                break
    else:
        flag = False
        
    return flag
```


```python
num = 8

if(isPrime(num)):
    print(num,"is Prime")
else:
    print(num,"is NOT Prime")
```

    8 is NOT Prime



```python
num = 13

if(isPrime(num)):
    print(num,"is Prime")
else:
    print(num,"is NOT Prime")
```

    13 is Prime


### Sum of square of first and last 2 digits


```python
def void(num):
    if num not in range(1000,9999):
        return -1
    else:
        first = int(num/100)
        last = num%100
        return first**2 + last**2
        
```


```python
res = void(num)
if res == -1:
    print("Invalid input!!")
else:
    print("Calculated result: ",res)
```

    Calculated result:  3394


<br /><br />

### Check for Vowel


```python
def isVowel(char):
    vowels = ['a','e','i','o','u']
    flag = False
    
    if char in vowels:
        flag = True
    
    return flag
```


```python
# prints True if passed charector is a Vowel
print(isVowel('u'))
print(isVowel('k'))
print(isVowel('m'))
print(isVowel('i'))
```

    True
    False
    False
    True


<br />

---
<br /><br /><br />
