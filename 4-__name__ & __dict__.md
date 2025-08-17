# Special variable name and dict

## __ __name__ __
> در پایتون هر فایل به چشم کلاس دیده میشود
>  اگر در داخل یک فایل فایل دیگر را `import` کنیم از همان جا ان فایل اجرا میشود

خروجی  __ name __ در خود فایل "__ main __ " است 
خروچی __ name __ در فایل دیگر اسم ان فایل است   

پس این
```python 
if __name__ == "__main__":
```
نشان دهنده این است که ایا این فایل به حیث فایل اصلی اجرا میشود

### __Ex-1__
___
__A.py__
```python
print(__name__)
```
> Output : __main__

__B.py__
```python
import A
```
> Output : A


___


## __ __dict__ __
دیکشنری یا لیست از instance attribute های یک object را میدهد

### Ex-1
```python
class Car:
	wheel = 4
	door = 4
	def __init__(self,color,maxSpeed):
		self.color = color
		self.maxSpeed = maxSpeed
mycar = Car("red", 400)
print(mycar.__dict__)
```
> Output : {'color': 'red', 'maxSpeed': 400}