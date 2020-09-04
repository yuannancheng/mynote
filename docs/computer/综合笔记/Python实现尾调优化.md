# Python实现尾调优化

---

在Python中使用 '**return** + 函数名()' 可以实现尾调用，即调用某函数后立即结束当前函数。
但是Python最多只能尾调 1000 次，超出则会报错。

<br>

**以下是通常的尾调示例：**

```python
def a(e):
	print('%s'%e)
	return a(e + 1)
a(1)
```
**结果：**

```python
1
2
3
...
995
996
RecursionError: maximum recursion depth exceeded while calling a Python object
```
在尾调深度超过 1000 以后就会报错，无法进一步尾调。

<br>

#### 一个牛人想出了解决方法

以下代码定义一个装饰器（适用于Python3+）
```python
# 低版本Python改成 class TailRecurseException:
class TailRecurseException(BaseException):
    def __init__(self, args, kwargs):
        self.args = args
        self.kwargs = kwargs

def tail_call_optimized(g):
    """
    This function decorates a function with tail call
    optimization. It does this by throwing an exception
    if it is it's own grandparent, and catching such
    exceptions to fake the tail call optimization.

    This function fails if the decorated
    function recurses in a non-tail context.
    """
    def func(*args, **kwargs):
        f = sys._getframe()
        # 为什么是grandparent, 函数默认的第一层递归是父调用,
        # 对于尾递归, 不希望产生新的函数调用(即:祖父调用),
        # 所以这里抛出异常, 拿到参数, 退出被修饰函数的递归调用栈!
        if f.f_back and f.f_back.f_back \
                and f.f_back.f_back.f_code == f.f_code:
            # 抛出异常
            raise TailRecurseException(args, kwargs)
        else:
            while 1:
                try:
                    return g(*args, **kwargs)
                # 低版本Python改成 except TailRecurseException, e:
                except TailRecurseException as e:
                    # 捕获异常, 拿到参数, 退出被修饰函数的递归调用栈
                    args = e.args
                    kwargs = e.kwargs
    func.__doc__ = g.__doc__
    return func
```

然后上面的示例改成如下：

```python
@tail_call_optimized
def a(e):
	print('%s'%e)
	return a(e + 1)
a(1)
# 实际使用时注意加停止调用的条件，否则会一直循环调用
```

<br>

#### 更新_20200409：

---

新发现，如果尾调循环的入口函数没有设定形参，而循环内部的某个函数却设定了形参，则会报一个错误：

```python
	return g(*args, **kwargs)
TypeError: calculatingTime() takes 0 positional arguments but 1 was given
```

<br>

我的也不知道是什么原因，但找到了 **解决方法：**

给入口函数设定一个带默认值的形参
```python
def functionName(NULL=''):
```
这样就可以解决此类问题。



{docsify-updated}