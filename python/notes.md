### Object Method
Method which has "self" as it's first argument.

```python
class Item:
  def calculate(self):
    pass

...

item.calculate() # "item" is passed as "self" argument for calculate()
```

### Magic method / Dunder method
This are the methods with special purpose.
```python
__<method name>__()
```

For example, item = Item() automatically calls \__init__()

### Optional Argument
qty is an optional argument in example gicen below
```python
def calculate(self, price, qty = 0)
```

### Attributes
We can create object attributes even after crearing an object.
```python
item.has_numpad = False
```
Here has_numpad is not initialised in \__init__(). This attribute is only for "item" object and not available in other object of class Item.

### Typing

```python
def __init__(self, name: str, price: int, qty = 0)
```
This will throw error if any data type other than string is passed as "name".
The "qty" argument does not need a type to be specified because, type is implecit in the default value "0" (integer).

### Input Validation

```python
def __init__(self, price,: int, qty = 0):
  assert price >= 0, f"Price {price} is negative"
  assert qty >= 0, "Invalid Qty"

  # do attribute initialisation
  ...
```
If assertion fails, it throws AssertionError along with the message speficied in the string.

### Instance representation
To print instance in meaningful way

\__repr__() returns string representation of instance. repr() calls \__repr__(). It is considered "official string representation of an instance.
```python
def __repr__(self):
  return f"Item('{self.name}', {self.price}, {self.qty})"
```

str() converts the input to string object. str() calls \__str__(). print() by default converts its argument to string before printing.
```python
print(str(obj)) is same as print(obj)
```
print() tries to find a nice way of prinitng instance. It checks for \__str__() first. It it's not present then it checks for \__repr__().

## Class Members

### Class Attributes
```python
class Item:
  pay_rate = 0.8 # classs attribute as it is initialised in the scope of class instead of as self.pay_rate inside __init__().

....
Item.pay_rate
item.pay_rate
```
Class attributes can be accessed using class or object. System first checks the attribute in object and then inside class.
Class attributes are considered $static$, there is no separate way of defining static attributes.

\__dict__ is a magic attribute.
```python
Item.__dict__ #contains all class attributes
item.__dict__ #contains all instance attributes
```
Class attributes are accessed inside instance method using class name.
```python
def apply_discount(self):
  self.price = self.price * Item.pay_rate
```

We can change "pay_rate" only for specific instance.
```python
def apply_discount(self):
  self.price = self.price * self.pay_rate

...
item1.apply_discount()
item2.pay_rate = 0.7
item2.apply_discount()
```

### List all instances of class
```python
class Item:
  all = []
  def __init__(self):
    ...
    Item.all.append(self)
```

### Class method
Class method take class as argument, "cls".
Class methos should do something that is related with the class, but usually, those are used to manipulate different structures of data to instantiate objects.
For example, object instantiation from csv file.
```python
import csv
class Item:
  @classmethod
  def read_from_csv(cls):
    with open('item.csv', 'r') as f:
      reader = csv.DictReader(f)
      items = list(reader)
      for itm in items:
        Item(
          name = itm.get('name'),
          price = float(itm.get('price')),
          qty = int(itm.get('qty'))
        )
    
```

### Static method
Static method never take class (cls) or instance (self) as argument
Static method should do something that is related with the class, but not something that must be unique per instance.
```python
class Item:
  @staticmethod
  def is_integer(num):
    if isinstance(num, float):
      return num.is_integer()
    elif isinstance(num, int):
      return True
    else:
      return False
...
print(Item.is_integer(7.0))
```

Class method / Static method can be called using instance.


### \__new__ vs \__init__:
\__new__() is a static method and it takes clas name as argument "cls". 
It gets called before \__init__() during instance creation and it allocates memory for an instance. 
Once the memory is allocated then \__init__() is called which initialises the instance attributes.
\__new__() is used in design pattern like singleton where instace creation is need to be controlled.
```python
class Logger(ABC):
  _logger = None
	_lock = Lock()
	def __new__(cls):
		if not cls._logger:	
			with cls._lock:
				if not cls._logger:
					cls._logger = super().__new__(cls)
		return cls._logger
```
## Inheritance
"super()" gives access to all attributes of parent class.

```python
class Item:
  def __init__(self, name: str, price: float, qty: int):
    ...

class Phone(Item):
  def __init__(self, name: str, price: float, qty = 0, broken = 0):
    super().__init__(name, price, qty)
    self.broken = broken

```
Get class name from instance:
```python
f"{self.__class__.__name__}"
```

## Encapsulation
Property and setter: Access to private /protected attributes.

Use property when you have to do some processing before returning an attribute.
```python
class Item:
  def __init__(self, quantity):
    self.__quantity = quantity # private attribute

  @property  # read-only attribute/ property decorator / getter
	  def quantity(self):
      # some processing
		  return self.__quantity

...
print(item.quantity)
```

Use setter when you have to do some processing before seting value to an attribute.
```python
  @quantity.setter
  def quantity(self, quantity: int):
    # some processing
    self.__quantity = quantity

...
item.quantity = 5
```

## Access modifiers
\__ (double underscore): Private. Allowed to access only inside enclosing class.

_ (single underscore): Protected. Allowed to access only inside enclosing class and subclasses.

no underscore prefix: Public. Anyone can access

```python
class Item:
  def __init__(self, name, price, qty):
    self.__name = name # private
    self._price = price # protected
    self.qty = qty # public
```
Same convention applies for methods.

Python does not restrict private or protected attributes with \__ or _ to be accessed outside the class.
Using \__ or _ is just Python naming convention for private or protected.

Python uses "Consenting Adults" philosophy: Assumes developer follow the convention of not accessing \__ or _ attributes outside the class.

### Name Mangling

## Polymorphism
For example, len() built-in function.

## Inheritance

### Interface

### Abstract class

## Multithreading

### Synchronisation using locks

## Errors

## Nested Class

## Decorators

## Doc Strings

## Package

## OOP tips for Python













