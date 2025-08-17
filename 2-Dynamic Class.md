# Dynamic Class
ساختن کلاس با دستور type
- سرعت این کلاس ها یک مقدار بیشتر است 
- میتوانیم بازنویسی کنیم (متدها و اتربیوت های انرا تغییر دهیم)

## Syntax 
```python
nameClass = type(" " , () , {})
```

```python
nameClass = type("explain" ,(inher) ,{"A":a}) 
```
"" ---> اسم مستعار (توضیعات)
( ) ---> برای حرث بری کلاس
{ } ---> هر متد که در کلاس است با اسم که با ان call شود

### Ex-1
```python
def constractor(self):
    pass
def catSound(self):
    print("mio mio")
    
Cat = type("My Dynamic class",(), {
    "__init__":constractor,
    "sound":catSound    
    })

tom = Cat()
tom.sound()
```
mio mio

