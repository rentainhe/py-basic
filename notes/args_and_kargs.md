## `*args` and `**kargs`

### 1. `*args`
传递一个`可变参数列表`给函数实参
```python
def test_args(first, *args):
    print('Required argument: ', first)
    print(type(args))  # tuple
    for v in args:
        print('Optional argument: ', v)  # 2, 3, 4

test_args(1, 2, 3, 4)
```
```
Required argument:  1
<class 'tuple'>
Optional argument:  2
Optional argument:  3
Optional argument:  4
```
- 可以传入多个参数, 这些参数会以`tuple`的形式组织起来

### 2. `**kargs`
将一个`可变关键字参数的字典`传给函数实参, 长度可以为0
```python
def test_kwargs(first, *args, **kwargs):
   print('Required argument: ', first)
   print(type(kwargs))
   for v in args:
      print ('Optional argument (args): ', v)
   for k, v in kwargs.items():
      print ('Optional argument %s (kwargs): %s' % (k, v))

test_kwargs(1, 2, 3, 4, k1=5, k2=6)
```
```
Required argument:  1
<class 'dict'>
Optional argument (args):  2
Optional argument (args):  3
Optional argument (args):  4
Optional argument k2 (kwargs): 6
Optional argument k1 (kwargs): 5
```

### 3. 调用函数过程中使用`*args`和`**kargs`
类似于`pack`和`unpack`操作, 元组的打包和解包
```python
def test_args_kwargs(arg1, arg2, arg3):
    print("arg1:", arg1)
    print("arg2:", arg2)
    print("arg3:", arg3)

args = ("two", 3, 5)
test_args_kwargs(*args)
```
```
arg1: two
arg2: 3
arg3: 5
```
```python
kwargs = {"arg3": 3, "arg2": "two", "arg1": 5}
test_args_kwargs(**kwargs)
```
```
arg1: 5
arg2: two
arg3: 3
```


## References
- [知乎大佬解读](https://zhuanlan.zhihu.com/p/50804195)