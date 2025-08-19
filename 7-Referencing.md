# Referencing
==نیاز به عکس دارد و تشریح دارد==




## int & float

### Ex-1
```python
x = 2
y = 3
z = x

print(id(x))
print(id(y))
print(id(z))

z += 1
print()
print(id(x))
print(id(z))
```

```output
140705208404440
140705208404472
140705208404440

140705208404440
140705208404472
```



## list & dict

### Ex-1
```python 
lst1 = [1,2,3,4,5]
lst2 = lst1 

print(id(lst1))
print(id(lst2))

lst1.append("OK")

print(id(lst1))
print(id(lst2))

print(lst1)
print(lst2)
```

```output
2146901170432
2146901170432

2146901170432
2146901170432

[1, 2, 3, 4, 5, 'OK']
[1, 2, 3, 4, 5, 'OK']
```

### Solution-Slice
```python
lst1 = [1,2,3,4,5]
lst2 = lst1[:]

print(id(lst1))
print(id(lst2))

lst1.append("OK")

print(lst1)
print(lst2)
```

```output
2330646878464
2330646876544

[1, 2, 3, 4, 5, 'OK']
[1, 2, 3, 4, 5]
```

### Solution-*Shallow Copy*-Copy
```python
lst1 = [1,2,3,4,5]
lst2 = lst1.copy()

print(id(lst1))
print(id(lst2))

lst1.append("OK")

print(lst1)
print(lst2)
```

```output
2275962263808
2275962261888

[1, 2, 3, 4, 5, 'OK']
[1, 2, 3, 4, 5]
```

### Trouble of *Shallow Copy*
```python 
lst1 = [1,2]
lst2 = [1,2,3,lst1,4]
lst3 = lst2.copy()  

print(id(lst2))
print(id(lst3))

lst1.append("OK")

print(lst2)
print(lst3)
```

```output
1765315449216
1765315738368

[1, 2, 3, [1, 2, 'OK'], 4]
[1, 2, 3, [1, 2, 'OK'], 4]
```

### Solution-deepcopy
> تمام رفرنس های داخلی انرا هم دوباره میسازد
```python 
from copy import deepcopy
lst1 = [1,2]
lst2 = [1,2,3,lst1,4]
lst3 = deepcopy(lst2)

print(id(lst2))
print(id(lst3))

lst1.append("OK")

print(lst2)
print(lst3)
```

```output
1804516202752
1804519326400

[1, 2, 3, [1, 2, 'OK'], 4]
[1, 2, 3, [1, 2], 4]
```



## Class

### Ex-1
```python 
class Car:
	def __init__(self,color,value):
		self.color = color
		self.value = value
		
car1 = Car("cheery", 25)
car2 = car1

print(id(car1))
print(id(car2))

car1.value = 500

print(car1.value)
print(car2.value)
```

```output
2558047445568
2558047445568

500
500
```

### Solution-*Shallow copy*-import copy
```python
from copy import copy

class Car:
	def __init__(self,color,value):
		self.color = color
		self.value = value
		
car1 = Car("cheery", 25)
car2 = copy(car1)

print(id(car1))
print(id(car2))
```

```output
1993756598608
1993756812224
```

### Solution-deepcopy
> برای کلاس ها هم به درستی کار میکند   



## str 

### Ex-Trouble
```python 
from copy import copy, deepcopy
str1 = "eqbal"
str2 = str1
str3 = copy(str1)
str4 = str1[:]
str5 = str1 + ""
str6 = deepcopy(str1)

print(id(str1))
print(id(str2))
print(id(str3))
print(id(str4))
print(id(str5))
print(id(str6))
```

```output
2423424637840
2423424637840
2423424637840
2423424637840
2423424637840
2423424637840
```

### Solution
```python 
str1 = "eqbal"
str2 = str1[::-1][::-1]

print(id(str1))
print(id(str2))
```

```output
2350279120224
2350279122240
```
