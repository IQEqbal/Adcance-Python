# Dunder Method del, add, new

> برای حذف variable یا object از RAM از دستور `del` استفاده میکنیم
```python
x = 5
del x
```

بیشتر Dunder Method ها را ما call نمیکنیم به اساس event های خاص خودشان call میشوند

##  __ __del__ __
زمانی call میشود که object از RAM حذف شود

### Ex-1
```python
class A:
	def __del__(self):
		print("Done")
a = A()
del a 
```
> Output : Done
##  __ __add__ __
زمانی Call میشود که object با یگ چیزی جمع شود

### Ex-Usage instructions
```python
class Sum:
	def __init__(self,value):
		self.value = value
	def __add__(self,other):
		return self.value + other

s = Sum(4)
print(s + 24)
```
> Output : 28

## __ __new__ __

قبل از `__init__` اجرا میشود
وظیفه ان ساختن object از روی کلاس است

### Ex-Usage instructions 
```python
class A :
	def __init__(self):
		pass
	def __new__(cls):
		pass
		return object.__new__(cls)
```
> این متد در تمام کلاس ها وجود دارد اگر override کردیم باید return انرا درست بنویسیم