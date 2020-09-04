# 关于Excel自定义TEXTJOIN函数、SWITCH函数

---

# TEXTJOIN函数：

TEXTJOIN函数是Excel在2016版本推出的新函数。

它能将某一区域的单元格值用某一符号拼接成一串文字。

比如：

有 “好久不见” 和 “你还好吗” 两个单元格，想用逗号把它们连接起来组成一句话，就可以这样做：



 ![1](.\关于Excel自定义TEXTJOIN函数、SWITCH函数.src.image\1.png)

TEXTJOIN函数的语法：`=TEXTJOIN( 连接符, 是否忽略空值, 需要合并的对象)`

 

# SWITCH函数：
学过编程的应该都不陌生，它类似于嵌套多层IF函数，但用起来却非常高效。

用法示例如图：



![2](.\关于Excel自定义TEXTJOIN函数、SWITCH函数.src.image\2.png)

SWITCH函数的语法：`=SWITCH( 需要判断的对象,  值1, 结果1, 值2, 结果2, ......... )`

SWITCH函数最多可以添加126个供匹配的值

看了上面，你一定觉得这两个函数很方便吧？

但是：

TEXTJOIN函数在Excel2016 365及以上版本才有，也就意味着，绝大部分用户都无法使用这个函数，如果需要使用就得安装2016 365以上版本。

SWITCH函数是和TEXTJOIN函数一同发布的，同样需要365以上版本才能使用。

 

**但是，为什么不自己写一个类似的函数呢？**

我在网上找了许久，东拼西凑，总算找到了类似的代码，但是他们和官方的函数还有一些差别，我修改了一下，使它们基本和官方的函数一模一样。这样，我们就可以在低版本的Excel中使用这两个函数了。

# 自定义函数方法：

1、下载函数包（[CSDN资源](https://download.csdn.net/download/weixin_44549795/12247750)  或  [百度网盘](https://pan.baidu.com/s/1m859dJlj4pNA6AbwgnTmpQ) 提取码: Love）

2、得到如图所示的文件：

![3](.\关于Excel自定义TEXTJOIN函数、SWITCH函数.src.image\3.png)

3、双击打开，这时候会启动Excel，它会提示一个警告：

![4](.\关于Excel自定义TEXTJOIN函数、SWITCH函数.src.image\4.png)

4、这时候需要点击启用宏（启用宏才能运行自定义函数）

5、启用宏之后，就打开了这个文件。但是看起来什么也没有，因为这是一个加载宏文件。可以试试按下 Alt + F11 键以打开 VB编辑器 ，就可以看到这两个函数的源码了。如图：

![5](.\关于Excel自定义TEXTJOIN函数、SWITCH函数.src.image\5.png)

6、关闭这个界面

7、现在需要把这个文件添加到启动项，以便你每次打开Excel都会加载这两个函数

8、点击 “文件” => 点击 “选项”（你需要启用 “开发者工具” ）：

![6](.\关于Excel自定义TEXTJOIN函数、SWITCH函数.src.image\6.png)

9、启用开发工具：

![7](.\关于Excel自定义TEXTJOIN函数、SWITCH函数.src.image\7.png)

10、将自定义宏添加到加载项：

![8](.\关于Excel自定义TEXTJOIN函数、SWITCH函数.src.image\8.png)

 11、完成，这时已经可以使用这两个函数了：

![9](.\关于Excel自定义TEXTJOIN函数、SWITCH函数.src.image\9.png)

<br>**值得注意的是：添加到启动项后Excel会将宏文件拷贝一份到 “C:\Users\用户名\AppData\Roaming\Microsoft\AddIns” 里面，此时你可以把下载的那个文件删除了，不会影响使用。**

 

# 源代码：
## TEXTJOIN函数：

```vb
' 自定义TEXTJOIN函数
Function TEXTJOIN(merger, ignore, ParamArray arr())
    Dim A As Variant, B As Variant, Mstr$
    If IsMissing(merger) Then merger = " "
    If Not IsMissing(arr) Then
        For Each A In arr
            If IsArray(A) Then
                For Each B In A
                    If ignore = 0 Or B <> "" Then Mstr = Mstr & merger & B
                Next
            Else
                If ignore = 0 Or A <> "" Then Mstr = Mstr & merger & A
            End If
        Next
    End If
    If Len(Mstr) Then TEXTJOIN = Mid(Mstr, 1 + Len(merger))
End Function
```

## SWITCH函数：
```vb
' 自定义SWITCH函数
Function SWITCH(Obj, ParamArray va())
    Application.Volatile True
    Dim i%
    For i = 0 To UBound(va) Step 2
        If va(i) = Obj Then
            SWITCH = va(i + 1)
            Exit Function
        End If
    Next
    SWITCH = False
End Function
```



{docsify-updated}