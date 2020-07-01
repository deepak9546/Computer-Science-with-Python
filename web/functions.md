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
