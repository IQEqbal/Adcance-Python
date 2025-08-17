# Constant :
یک مقدار حافظه (variable) است که مقدار ان بعد از initialize قابل تغییر نیست 
*پایتون به صورت Built in ندارد*

# قوانین که مفهوم میرساند یک متغیر Constant است :

### 1.  تمام حرف variable بزرگ نوشته شود
```python
NAME = "eqbal"
```

### 2. تفریف فانکشن
```python
def name():
	return "eqbal"
```

### 3. استفاده از حافظه slots  
متغیر های که داخل حافظه slots است قابل تغییر هستن اما بصورت دیفالت قابل تغییر نیستن

> حافظه slots برای ساختن constant ساخته نشده است 
> متغیر ها در داخل حافظه slots حافظه کم و سرعت دسترسی بالایی دارند

```python
class Constants:
	__slots__ = ()
	name = "eqbal"
	Pi = 3.14

const = Constants()
const.name = "cyber"
```
AttributeError: 'Constants' object attribute 'name' is read-only