## `class` in python

### 1. 类中定义的方法必须有额外的第一个参数`self`
```python
class Test:
    def prt(self):
        print(self)  # <__main__.Test instance at 0x10d066878>
        print(self.__class__)  # __main__.Test
t = Test()
t.prt()
```
- `self`表示类的`实例`
- `self.__class__`则指向类
- `self`并非关键字, 可以被替换

### 2. 添加 修改 删除类的属性
```python
class Test:
    def __init__(self, a):
        self.a = a
t = Test(1)
t.age = 7  #  添加age属性
t.age = 8  #  修改age属性
del t.age  #  删除age属性
```
还可以通过python的内置方法来访问属性
- `getattr(obj, name[, default])`: 访问对象属性
- `hasattr(obj, name)`: 检查是否存在一个属性
- `setattr(obj, name, value)`: 设置一个属性, 如果不存在, 会创建一个新属性
- `delattr(obj, name)`: 删除属性
```python
hasattr(t, 'age')    # 如果存在 'age' 属性返回 True。
getattr(t, 'age')    # 返回 'age' 属性的值
setattr(t, 'age', 8) # 添加属性 'age' 值为 8
delattr(t, 'age')    # 删除属性 'age'
```

### 3. Python内置类属性
- `__dict__` 类的属性（包含一个字典，由类的数据属性组成）
- `__doc__` 类的文档字符串
- `__name__` 类名
- `__module__`
- `__bases__`
```python
class Test:
    ...
# Test.__doc__
# Test.__module__
# Test.__bases__
```
