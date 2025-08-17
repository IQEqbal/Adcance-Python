> وقتی یک متد یا اتربیوت private تعریف میشود دیگر نمیتوان خارج از کلاس به ان دسترسی داشت
> در پایتون به صورت Built in وجود ندارد 

## Weakly Private
متدها و اتربیوت های که با یک اندرلاین ( _ ) شروع میشوند    
خارج از کلاس قابل دسترسی است

## Strongly Private
متدها و اتربیوت های که با دو اندرلاین ( __ ) شروع میشوند    
نام ان در RAM تغییر میکند 

### Ex-1
```python
class A:
	def __init__(self):
		self.val = 2    # RAM ---> val
		self._val = 4   # RAM ---> _val
		self.__val = 6  # RAM ---> _A__val

a = A()
print(a.val)   
print(a._val)
print(a.__val)
```
> error

### Ex-2
```python
class A:
	def __init__(self):
		self.val = 2    # RAM ---> val
		self._val = 4   # RAM ---> _val
		self.__val = 6  # RAM ---> _A__val

a = A()
print(a.val)   
print(a._val)
print(a._A__val)
```
> 2
> 4
> 6

## Ex-From two different Files
> در پایتون هر فایل به چشم class دیده میشود 

### Ex1-From two different Files
---
__file1.py__
```python
class A :
	def __init__(self):
		self.val = 2    
		self._val = 4   
		self.__val = 6
```
__file2.py__
```python
from file1 import *
a = A()
print(a.val)   
print(a._val)
print(a._A__val)
```
> 2
> 4
> 6
___

### Ex2-From different Files
---
__file1.py__
```python
val = 2
_val = 4
__val = 6
```
__file2.py__
```python
import file1
print(file1.val)
print(file1._val)
print(file1.__val)
```
> 2
> 4
> 6

__file3.py__
```python
from file1 import *
print(val)    #---> 2
print(_val)   #---> error
print(__val)  #---> error
```
> error
___
