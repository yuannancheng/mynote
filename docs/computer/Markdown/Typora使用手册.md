# Typora使用手册

---



# 目录


```markdown
[toc]
```

# 标题



```markdown
#       一级标题
##      二级标题
###     三级标题
####    四级标题
#####   五级标题
######  六级标题 
```



# 一级标题

# 二级标题

###     三级标题
####    四级标题
#####   五级标题
######  六级标题 

# 引用


```markdown
> 一级引用
> > 二级引用
> > > 三级引用...
```


> 一级引用
> > 二级引用
> >
> > > 三级引用...

# 代码


```markdown
`单行代码`
```

`单行代码`


~~~markdown
```python
多行代码
多行代码
```
~~~

```markdown
多行代码
多行代码
```

# 列表


```markdown
* 无序列表1
+ 无序列表2
- 无序列表3
```


* 无序列表1
+ 无序列表2
- 无序列表3


```markdown
- 多行无序列表1
	* 多行无序列表2
		* 多行无序列表3
```

- 多行无序列表1
	* 多行无序列表2
		* 多行无序列表3


```markdown
1. 有序列表1
2. 有序列表2
3. 有序列表3
```


1. 有序列表1
2. 有序列表2
3. 有序列表3


```markdown
1. 多行有序列表1
2. 多行有序列表2
	1. 多行有序列表2-1
	2. 多行有序列表2-2
3. 多行有序列表3
	1. 多行有序列表3-1
	2. 多行有序列表3-2
```

1. 多行有序列表1
2. 多行有序列表2
	1. 多行有序列表2-1
	2. 多行有序列表2-2
3. 多行有序列表3
	1. 多行有序列表3-1
	2. 多行有序列表3-2

# 单选框

```markdown
- [ ] 单选框1
- [x] 单选框2
```


- [ ] 单选框1
- [x] 单选框2

# 表格

```markdown
| 姓名 | 性别 | 年龄 |    手机号 |
| :--- | :--: | :--: | --------: |
| 张三 |  男  |  21  | 123456789 |
| 李四 |  女  |  23  | 123456789 |
| 王五 |  男  |  25  | 123456789 |
```


| 姓名 | 性别 | 年龄 |    手机号 |
| :--- | :--: | :--: | --------: |
| 张三 |  男  |  21  | 123456789 |
| 李四 |  女  |  23  | 123456789 |
| 王五 |  男  |  25  | 123456789 |

# 图片


```markdown
![图片](../../../_media/logo.png)
```

![图片](../../../_media/logo.png)

# 超链接

行内式链接（当前标签页打开）：
```markdown
[百度](https://www.baidu.com/)
```
[百度](https://www.baidu.com/)

参考式链接（新标签页打开）：
```markdown
[CSDN网址][CSDN网址]
[CSDN网址]:https://www.csdn.net/
```
[CSDN网址][CSDN网址]

[CSDN网址]:https://www.csdn.net/

自动链接：
```markdown
<https://github.com>
```
<https://github.com>

# 斜体

```markdown
*斜体1*
_斜体2_
```

*斜体1*

_斜体2_

# 粗体


```markdown
**加粗1**
__加粗2__
```


**加粗1**

__加粗2__

# 下划线

```markdown
<u>下划线</u>
```

<u>下划线</u>

# 删除线


```markdown
~~删除线~~
```

~~删除线~~

# 分隔线

分隔线1：
```markdown
***
```

***

分隔线2：
```markdown
---
```

---

分隔线3：
```markdown
___
```

___

# 脚注


```markdown
Typora[^1]
[^2]A markdown editor

[^1]: 注脚1
[^2]: 注脚2
```

Typora[^1], A markdown editor[^2]

<sub>此处语法无误，只是因为Docsify不支持脚注</sub>

[^1]: 注脚1
[^2]: 注脚2

# 上下标


```markdown
3^2^ = 9
H~2~O
```

3<sup>2</sup> = 9

H<sub>2</sub>O

<!-- 因为 Docsify 不支持渲染 Markdown 的上、下标，所以在这里实际上使用的是<sup></sup>和<sub></sub> -->

# 常用符号

```markdown
\\		反斜线
\`		反引号
\*		星号
\_		底线
\{ \}	花括号
\[ \]	方括号
\( \)	括弧
\#		井字号
\+		加号
\-		减号
\.		英文句点
\!		惊叹号
```

\\   反斜线<br>
\`   反引号<br>
\*   星号<br>
\_   底线<br>
\{ \}  花括号<br>
\[ \]  方括号<br>
\( \)  括弧<br>
\#   井字号<br>
\+   加号<br>
\-   减号<br>
\.   英文句点<br>
\!   惊叹号<br>

# 特殊符号

```markdown
&copy;		版权
&reg;		注册商标
&trade;		商标
&nbsp;		空格
&amp;		和号
&quot;		引号
&apos;		撇号
&lt;		小于号
&gt;		大于号
&ne;		不等号
&le;		小于等于
&ge;		大于等于
&cent;		分
&pound;		磅
&euro;		欧元
&yen;		元
&sect;		节
&times;		乘号
&divide;	除号
&plusmn;	正负号
```

&copy;       版权<br>
&reg;       注册商标<br>
&trade;       商标<br>
&nbsp;         空格<br>
&amp;       和号<br>
&quot;        引号<br>
&apos;         撇号<br>
&lt;       小于号<br>
&gt;       大于号<br>
&ne;       不等号<br>
&le;       小于等于<br>
&ge;       大于等于<br>
&cent;       分<br>
&pound;       磅<br>
&euro;       欧元<br>
&yen;       元<br>
&sect;       节<br>
&times;       乘号<br>
&divide;       除号<br>
&plusmn;       正负号<br>

# 数学公式

[导入LateX语法](./LateX语法.html ':include :type=iframe width=100vw height=600vh')

---

# 附录

- [HTML特殊字符编码对照表][HTML特殊字符编码对照表]

[HTML特殊字符编码对照表]:https://www.jb51.net/onlineread/htmlchar.htm "HTML特殊字符对照表"

- [Typora基础语法][Typora基础语法]
[Typora基础语法]:https://www.jianshu.com/p/a6a6a22e9393	"Typora基础语法"

- [LateX数学公式语法][LateX语法]
[LateX语法]:http://lixingcong.github.io/2016/04/04/LaTex-intro/	"LaTex数学公式语法"



{docsify-updated}