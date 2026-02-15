---
title: 01_Basics of Python
description: Basis fundamentals of pyton
author: codedloki
series: porgramming,python
date: 15-02-2026
tags:
  - python
---

# Basics of Python

#python #basicpython

Python  is an interpreted language . It is widely used in developing cybsecurity tools  and Ai application 

 It has wide range of librariues


## Data Types

#datatypes



| Data Type              | Examples          |
| ---------------------- | ----------------- |
| Integer        numbers | -2, -1, 0, 1, 2,  |
| floating       numbers | -1.25,0.5,1.24    |
| Strings                | 'a' , 'aa' ,'aba' |




  ### Operations On Strings 


- ####   Concatenation of Strings


Concatenation  is joining of  two or more string  . Concatenation can be done between two strings only not possible between different data types

```python
>>> 'Alice' + 'Bob'
```




### Boolean Values 

integer , string and float data type have unlimited number of possible values the boolean data type has only  two possible value `True`  or `False`


Eg :

```python
spam = True
```



##  Variables
#varibles


Variables are like containers  which hold specific type of data 

It can only be one word . can contain alphabets numbers and underscore but it cannot start with number

Eg :

```python

spam = "goodbye"
count = 3

# these are comments which can be used to explain the code to other developer 


sp = 5
lm = 3

n = sp + lm

print(n) #output will be 8 as we are performing arithmentic operation


```




### Basic Program and taking user input 

```python

print("What is your name ?") # this is used to print message to the screen
username = input() # input function is used to take input from user 

# the input() function accepts data from user in string format 


print(username +" is  agood name") # this is form of string concatenation 
# where strings are joint together we take name from user and print it here

print(len(username)) # len() function is used to find length of string (no of characters in a string)


print("Whats ur age ?") # now here we want age of user but the age should be a integer value but input accepts in string  


# in these condition here we have some special functions str(), int(),float()


# these functions are used for typecasting in python i.e converting data from one data type to another 

# here we can  use  int function to convert string data received from user input to convert it into int data type making 


age = int(input())

print("You are currently" + str(age) + " years old" )

# the str function helps u convert data into string data type 

print("You will be " + str( age + 1 ) + "years old next year ")
# type casting into int can help u carry out arithmetic operations on the value of variable

```




## Operators

- ###  Comparison Operators :

Comparison  operators are used to compare two values and give out one boolean response value



| Operator | Meaning                  |
| -------- | ------------------------ |
| ==       | Equal to                 |
| !=       | Not equal to             |
| <        | Less Than                |
| >        | Greater Than             |
| >=       | Greater than or equal to |
|          |                          |

eg 

```python
42 == 42 
True

42 == 91 
False

'hello' == 'hello'
True

```




- ### Binary Boolean Operators

Below truth table shows evry possilble result of a boolean operaor 


( **And Operator**   Truth table )

| Expression      | Evaluates to |
| --------------- | ------------ |
| True and True   | True         |
| True and False  | False        |
| False  and True | False        |
| False and False | False        |
|                 |              |
**OR  operator** Truth Table


| Expression     | Evaluates |
| -------------- | --------- |
| True or  True  | True      |
| True or False  | True      |
| False or True  | True      |
| False or False | False     |

**NOT Operator** Truth Table


| Expression | Evaluates to |
| ---------- | ------------ |
| not True   | False        |
| not False  | False        |



**Mixing Boolean and Comparison Operators**


```python
(4 < 5) and (5 < 6)
True
(1==2) or (2==2)
True
```