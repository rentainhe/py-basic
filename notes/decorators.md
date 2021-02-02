## decorators usage

### 1. what is decorators ?
用来装饰python的工具, 是一种函数的函数, 传入的参数是一个函数, 通过实现各种功能对这个函数进行增强

### 2. Why use decorators ?
简单, 清晰

### 3. Usage examples
#### 计算函数运行时间
```python
# 不适用装饰器, 对于每个函数都需要写计算时间的代码, 冗余复杂
from time import time, sleep
def fun_one():
    start = time()
    sleep(1)
    end = time()
    cost_time = end - start
    print("func one run time {}".format(cost_time))
    
def fun_two():
    start = time()
    sleep(1)
    end = time()
    cost_time = end - start
    print("func two run time {}".format(cost_time))
```

```python
# 使用装饰器
from time import time, sleep
def run_time(func):
    def wrapper():
        start = time()
        func()                  # 函数在这里运行
        end = time()
        cost_time = end - start
        print("func three run time {}".format(cost_time))
    return wrapper

@run_time
def fun_one():
    sleep(1)

@run_time
def fun_two():
    sleep(2)
```
统计时间这几行代码在每个函数里是重复的, 所以可以统计包装成一个修饰器

## References
- [知乎大佬笔记](https://www.zhihu.com/question/325817179/answer/798679602)