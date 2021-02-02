## inheritance

### 1. `__init__`初始化
- 子类需要自动调用父类的构造方法
  - 显示地调用
  - 不重写
```python
class Father(object):
    def __init__(self, name):
        self.name = name
        print(self.name)
    def getName(self):
        return 'Father ' + self.name

class Son(Father):
    def getName(self):
        return 'Son '+self.name

if __name__=='__main__':
    son=Son('test')  # test 
    print ( son.getName() ) # Son: test 
```

- 如果重写了`__init__`, 就不会调用父类的`__init__`方法

- 如果重写`__init__`方法的同时仍然需要调用父类的初始化方法, 则需要使用`super`关键词
```python
class Father:
    def __init__(self, name):
        self.name = name
        ...
class Son(Father):
  def __init__(self, name):   
    super(Son, self).__init__(name)  # 使用super关键词
```