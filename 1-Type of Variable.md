# global , Local , nonlocal
---
## global :
در برنامه اصلی declare شده است
در داخل function فقط میتوانیم بخوانیم نمیتوانیم مقدار انرا تغییر دهیم (*پایتون فقط یک سطح بالا را نگاه میکند*)
برای اینکه تغییر داده بتوانیم باید رفرنس بتیم با کیورد `global` 
### Ex-1
```python
x = 2 
def myf():
	print(x)
myf()

```
2
### Ex-2
```python 
x = 2 
def myf():
	print(x)
	x += 2
	print(x)
myf()
```
error                     حتی 2 هم چاپ نمیکند

> وقتی بخواهیم قیمت را تغییر دهیم پایتون فکر میکند ان متغیر در scope ان وجود دارد 
### Ex-3
```python
x = 2
def myf():
	global x
	x += 2
	print(x)
myf()
print(x)
```
4
4

## local :
در داخل فانکشن declare میشود فقط در  scope ان فانکشن قابل دسترسی است

### Ex-1
```python
def myf1():
    x = 2
    def myf2():
        print(x)
    myf2()
myf1()
```
2

```python
def myf1():
	x = 2 
	def myf2():
		print(x)
		x += 2
	myf2()
myf1()	
```
error

## nonlocal :
### EX - global
```python
x = 1 
def myf1():
	x = 2
	def myf2():
		global x
		x += 10
		print(x)
	myf2()
	print(x)
myf1()
print(x)
```
11
2
11
### Ex - nonlocal
```python
x = 1
def myf1():
	x = 2
	def myf2():
		nonlocal x
		x += 10
		print(x)
	myf2()
	print(x)
myf1()
print(x)
```
12
12
1