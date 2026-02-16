---
title: Regular Expressions in python
author: codedloki
date: 16-02-2026
---
## INTRODUCTION

Patterns are widely used in our day to day life . for usinor defining patterns in python we use regular expression 

the search we perform in our editors are an application to regular expresssion 


python library used for this is  re which can imported by 

```python
import re
```



Passing a string value to ur regular expression to `re.compile()` returns  a regex object


> Note :
> `\d`  in regex is use to denote a digit character
> `r''`  r at starting of string can be used to make string a raw string


for eg : Regex for Phone number

```python

import re

phonenumregex = re.compile(r'\d\d\d-\d\d\d-\d\d\d\d') # phone number format goes like 444-555-666
mo = phonenumregex.search('My Number is 434-232-1212')
print(mo.group())
```

output

```shell
434-232-1212
```






## Steps for searching for data with regex


- **Step 1** : import re module
- **Step 2** : Create a regex object with re.compile()

	> Note : remember to use a string  while creating a regex object
	
- **Step 3** : pass the string you want to pass in search function of regex object
- **Step 4**: Call group method to  return string thaat actually match with the patttern  or raw string passed


## Grouping

Paranthesis have some speciaal importance in grouping 

the groups function returns a tuple of multiple values  you can  use multiple  assignment trickas in below code 

```python
import re

phonenum=re.compile(r'(\d\d\d)-(\d\d\d)-(\d\d\d\d)')
mob = phonenum.search('My number is 889-638-7473')
print(mob.groups()) # plural form of group
print(mob.group(1)) # prints the first thre digit group

cocode,areacode,randomcode = mob.group()


```


## Text pattern matching with Pipe


this below 

```python

import re
heroregex = re.compile(r'Batman|Tina Fey')
mob = heroregex.search('Tiny and Tina Fey')
mob.group()hmob = heroregex.search('Batman and Tina Fey')
mob.group()
```


findall method is used findall matching occurences



pipe **|**  will allow to check either occurence of either of string
like in above program it checks either ocurence of Batman or Tiney Fey



## Optional Matching with Question marks


This can  be used when u want to optionaly match a character whether or not the text is there


The **?** flags the group that preceeds it as an optional part of pattern


```python
import re

batregex= re.compile*(r'Bat(wo)?man')
mob1 = batregex.search("Adventures of Batman")
mob1.group()

mob2 = batregex.search("Adventures of Batwoman")
mob2.group()


mob3 = batregex.search('Adventures of Batwowowoman')
mob3.group()
```



## Matching Specific Pattern Repition  with Curly braces



This  can be useful when u have a group which u have to  repeat for specifc no of times 

example if u want to repeate ha string for 3 timesu can achive this simply by below form


```python
"(Ha){3}"
```

this will macth only HaHaHa  and not Ha or HaHa or HaHaHaHa


you can also specify range like min to max in below form 

```python
"(Ha){3,5}"
```


## Matching zero or more occurence with Star

The  *  is used to denote that the group that precedes the start can occur  zero or more number of times

 it can either me n  no of times or can be totally absent 

eg:
```python

import re

m1 = re.compile(r"Bat(wo)*man")
res1 = m1.search('This is Batman')
res1.group()

res2= m1.search("Hello r u Batwoman")
res2.group()
```



## findall() method


search() function returns the match object of first matched string where as in findall mothod it will return all matches string unlesss there are groups in the strng


```python

import re 

mobregex = re.compile(r'\d\d\d-\d\d\d-\d\d\d\d')
data = mobregex.findall('My number 999-235-7666 and your 273-626-7282')
print(data)
```


## Character Class 

Charcter class are short hands for various values for example

we learnt about /d before as a short hand for numric digits


here are soe more



| shorthand character | Represent                                                |
| ------------------- | -------------------------------------------------------- |
| \d                  | for numeric digits from 0 to 9                           |
| \D                  | Any charactter that is not  numeric between 0 to 9       |
| \w                  | Any letter numeric or underscore character               |
| \W                  | Any character that is not letter,numeric or underscore   |
| \s                  | Any space or new line character                          |
| \S                  | Any chracter that is not space ,tab or newline character |
|                     |                                                          |
## Making  Own Character Set



## Carret and Dollar sign


**^** This is the carrat sign . This is used to denote that string must begin with specific pattern

**$** This is dollar sign . It is used to denote that the string must end with given pattern


Eg

```python
import re

beginwith = re.compile(r'^Hello')
beginwith.search("Hello world") == None


endswith = re.compile(r'World$')
endswith.search('length of string world') == None
```



## Wildcard Character 

The . (dot)  character is a wild card in regular expression and it will match in any character  except for a new line 

Eg 

```python
atRegex =re.compile(r'.at')
atRegex.findall("The cat sat on a mat")
```

### Matching Everything with Dot Star


When combined, `.*` means: **"Match any character, any number of times."** It acts as a placeholder for "any text."


Eg 
if u want to match string "First Name" followed by any and all text followed by last name followed by anything use .*  (dot star) character

```python

import re

namereg = re.compile(r'First name:(.*) Last name:(.*)')
user = namereg.search('First name:John Last name:Wick')
user.group(1)
user.group(2)
```

The dot star uses **greedy** mode . it tries to match as much as text possible 

To match in non greedy mode use the question mark with the  ``.*``

The question mark tell program to match in non greedy way


```python
import re
nongreedyregx = re.compile(r'<.*?>')

mo = nongreedyregx.search("<To serve> man for dinner")
mo.group()
# Output :'<To serve>'
mo = nongreedyregx.search("<To serve> man for dinner>")
mo.group()
# '<To serve>'
greedyregx = re.compile(r'<.*>')
mo1 = greedyregx.search("<To serve> man for dinner>")
mo1.group()
# '<To serve> man for dinner>'

```


## Matching new lines with Dot character


Dot character match all characters except new line this can be bypassed 
by passing DOTALL as arguement to compile function


Ex:

```python
import re

newlineregex = re.compile('.*',re.DOTALL)
newlineregex.search('Serve Public Trust.\nProtect innocent \n \n Uphold the law').group()

```


## Case Insensitive Matchiing

Normal regular expression  match text with exact  casing  u specifiy ( a -> a )

but somethimes u might want only to letters to match and no casing importance 
whether they are upper case or lower case 


To make it case insensitive make  pass re.IGNORECASE or re.I  as second arguement to re.compiler



```python

import re

robocop = re.compile(r'robocop',re.I)
robocop,search("RoBoCop is just a dream").group()
```



## Managing Complex Regular expression


Regular Expressions are fine if they are short or smaller but it grows in size it becomes difficult to manage and read them 

you can migrate this by telling re.compile to ignore whitespaces and comments inside regular expresssion string


The verbose mode can be enabled  by ppassing  variable as  re.VERBOSE as second arguement to re.compile()


instead of hard regular expression as below

```python
phoneRegex = re.compile(r'((\d{3}|\(\d{3}\))?(\s|-|\.)?\d{3}(\s|-|\.)\d{4} (\s*(ext|x|ext.)\s*\d{2,5})?)'
```



you can spread the regular expression over multiple lines with comments  
like this:  



```python
phoneRegex = re.compile(r'''(  
(\d{3}|\(\d{3}\))? # area code  
(\s|-|\.)? # separator  
\d{3} # first 3 digits  
(\s|-|\.) # separator  
\d{4} # last 4 digits  
(\s*(ext|x|ext.)\s*\d{2,5})? # extension  
)''', re.VERBOSE)
```