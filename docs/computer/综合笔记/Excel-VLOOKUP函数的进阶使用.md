# Excel-VLOOKUP函数的进阶使用

---

Excel相信大家不会陌生，其中有大量内置的函数可供用户调用，用于帮助用户处理某些复杂且繁琐的问题，功能非常强大。

由于昨天我在使用Excel时深刻地感受到了技术的力量，所以不禁想要将昨天使用Excel的心得分享给大家。

情况是这样的：毛概老师要求我给班上同学进行分组，便于以后对平时成绩的统计。为了考虑大家的感受，我便让大家自己决定和哪些人一组，决定好后报给我统计。

于是，我便遇到一个较繁琐的事情：每一个同学报给我名字后，我需要去花名册里找到他对应的学号并复制到分组名单里对应的名字后面。

一发现这一繁琐的步骤，我便想到能否用Excel来帮我自动填充学号。

网上一搜，果然有一大把函数，筛选了一下，我发现VLOOKUP函数最适合我的需求。

先介绍一下VLOOKUP函数：

函数的结构是：

`=VLOOKUP( 查找值, 查找区域, 引用的列, 是否精确查找)`

用 *'('* 和 *')'* 括起来的内容，用 *','* 隔成了四个区域，这四个区域有一个专业名称叫做 *“参数”*，我们在使用函数时传入不同的参数可以达到不同的效果。

而我们学习如何使用一个函数也就是学习如何填写参数。

当然，这是我将官方文档翻译成我的理解后的提示，或许还是不太好理解。

没关系，上案例：

![img](.\Excel-VLOOKUP函数的进阶使用.src.image\aHR0cHM6Ly9tbWJpei5xcGljLmNuL21tYml6X3BuZy94aHdIaWFRUVcyZ3NuSVlRYzhCQndVNmNTRmRyYm1mMzhkQUhhV0ZIVFB2QVBaZWp6ZVY5VTRrRmtnRE56VVZiMGVHWWVvMjVxZndSV0toUnBlbFNnc3cvNjQw.jfif)


这里，可以看到 *'分组.xlsx'* 和 *'名单.xlsx'* 在同一文件夹内；

我们打开 *'分组.xlsx'* 来看看：

![img](.\Excel-VLOOKUP函数的进阶使用.src.image\aHR0cHM6Ly9tbWJpei5xcGljLmNuL21tYml6X3BuZy94aHdIaWFRUVcyZ3NuSVlRYzhCQndVNmNTRmRyYm1mMzh6OExNb3JVY1lnNjJhdXA3blZPZjcyTG96RDFEaHNDOVQzOGFETjc4ZXRPMThMSmF1NE5FOVEvNjQw.jfif)


成员那一列，就是学生的姓名，学号那一列就是要通过VLOOKUP函数来填充的学号，下面就是在学号那栏单元格中要输入的公式：

```powershell
=IF(C5="","",VLOOKUP(C5,'D:\Users\白茅纯束\Desktop\123\[名单.xlsx]Sheet1'!$A$2:$B$46,2,FALSE))
```

其中，最外层的IF函数用来判断姓名那栏是否为空。也就是说如果为空就不进行索引，如果有名字在那里就执行索引。这样做的好处是避免出现索引值为空而报错，出现一些不该出现的东西。

接下来一层就是VLOOKUP函数，我们来详谈：

第一个参数是C5，因为C5就是第一个成员姓名所在的单元格，也就是说在D5这个单元格里我们要引用它左边一个单元格C5里的数据进行索引。

第二个参数是一个地址，因为名单在另一个叫做 *'名单.xlsx'* 的文件里，我们要正确填写查找区域就必须填写文件的路径。

其中：D:\Users\白茅纯束\Desktop\123\ 表示文件所在的目录，[名单.xlsx] 表示文件名，Sheet1 表示文件中的工作簿名称，!$A$2:$B$46 表示在这一工作簿中引用的数据区域。

  

有人就要问了，A2前面为什么要加一个$符号呢？这是因为我们之后不可能给每一个同学的学号栏都输入这样长的一串公式，那样还不如直接去找学号简单。我们必须要用到填充功能。而填充过程中所有相对引用（没加$符的引用地址）都会被换成相应的地址。比如参数里的A2在向下填充一格时就会变成A3；这就导致我们引用的数据区域发生了变化，从而可能导致错误。所以为了避免这种情况，我们需要在相对引用地址前加一个$符号（当然也可以在选中文本的情况下用快捷键F4），将它变成绝对引用。

第三个参数用于确定你想要得到的那个数据所在的列。比如在下面下面这张图中，学号是我们需要得到的数据，那么学号在我们引用的区域中处于第几列呢？处于第2列。

所以在第三个参数这里我们填数字2就可以了。

![img](.\Excel-VLOOKUP函数的进阶使用.src.image\aHR0cHM6Ly9tbWJpei5xcGljLmNuL21tYml6X3BuZy94aHdIaWFRUVcyZ3NuSVlRYzhCQndVNmNTRmRyYm1mMzhSd2hyV1NkTGx2OEVNQWVTQm1aRTU5MTZwek9aWUZoVVV4YjBQTnVpYzZCVUZsTHY0bmhhMnBRLzY0MA.jfif)


接下来是第四个参数，第四个参数用于告诉Excel你是要精确查询还是模糊查询。这里我建议只要你知道精确的索引值，就填true，否则可能会发生某些不受你控制的事情。毕竟做数据这块讲究的就是数据的精确性，要是返回来一个连你也模棱两可的数据，估计你也不敢拿去用吧。

到这里，算是讲完了VLOOKUP函数的常规操作项。哎，细心的读者已经看到本文的标题是

Excel-VLOOKUP函数的进阶使用

对，作者在使用中发现，VLOOKUP函数的第二个参数呢，它大有可玩。

就是它不仅能填写本地的路径，还能填写任意一个能获取数据的地址！

哎呦！这真是太赞了![img](.\Excel-VLOOKUP函数的进阶使用.src.image\aHR0cHM6Ly9yZXMud3gucXEuY29tL21wcmVzL2h0bWxlZGl0aW9uL2ltYWdlcy9pY29uL2NvbW1vbi9lbW90aW9uX3BhbmVsL3NtaWxleS9zbWlsZXlfNzkucG5n.jfif)

有的人就要问了，这有什么区别呢？

区别大大的！

就比如，我这次分组要用到学生的学号信息，那下次或许还来一个啥表格呢？难道我要同样的在工作设备上整出一个名单表格来？这也太麻烦了吧。

还有就是，作者昨天使用这个函数时是在电脑上操作的，但是细心的人也看到了，五个组还有一大半同学的名字没填上去。那如果哪个同学临时要我帮他改分组，我肯定不可能再在电脑上整一遍。这时我自然是用手机给他改一下就行了，但是手机上并没有相对的文件路径。一改，那函数就不能索引到学号信息了。

这时，如果用一个文件链接来代替本地文件路径，就可以很好地解决这个问题。

微软在不知什么时候，已经开发出多人协作功能了。就是说，一个作者在一台设备写的文档，另一作者可以在另一设备上访问，如果获得授权的话，还能进行编辑。

这里，我们要用的就是微软提供的OneDrive服务。

首先，将名单文件另存为，将文件存到微软的服务器上

![img](.\Excel-VLOOKUP函数的进阶使用.src.image\aHR0cHM6Ly9tbWJpei5xcGljLmNuL21tYml6X3BuZy94aHdIaWFRUVcyZ3NuSVlRYzhCQndVNmNTRmRyYm1mMzgySWppYllCRHY4aWJsNW52M1RqbnhpYnAyOGliOUNLb1NUWjIwNHhTOVd4OWhDd1ZZYzlkdW13OG1nLzY0MA.jfif)

然后，复制文件地址

![img](.\Excel-VLOOKUP函数的进阶使用.src.image\aHR0cHM6Ly9tbWJpei5xcGljLmNuL21tYml6X3BuZy94aHdIaWFRUVcyZ3NuSVlRYzhCQndVNmNTRmRyYm1mMzhVVWlhODZpYmVHTTdZQmRBWlBXTG1SZFdnaWFrYWVpYUt6SXBzTlc3T1Z3cmRmT09aZDMyREc3b3h3LzY0MA.jfif)

然后，你就可以把你复制得到的地址粘贴到你的第二个参数里面了，最后公式是这样：

```powershell
=IF(C5="","",VLOOKUP(C5,'https://d.docs.live.net/***.xlsx[名单.xlsx]Sheet1'!$A$2:$B$46,2,FALSE))
```



为了保护班级同学的信息，我在这就用 ***** 来代替文件路径了。

这段改好后，下拉填充，你就可以在任意一台能联网的设备使用VLOOKUP函数来获取你要的数据了。

当然，微软的服务器毕竟远在美国，打开文件加载的时间可能会有点长，如果你想要更高的效率。那么，也可以将你的Excel文件存在某一个云服务商那里，然后设置一下访问权限，你就可以通过链接来访问你存在云端的表格了。常见的云存储比如 新浪云，百度云，阿里云等等，都提供云端数据存储服务，其他的我不知道，但是我知道新浪云每天有300M的免费流量，对于一个小表格来说，显然还是足够的了。

但是云端存储相对于微软的OneDrive而言的缺点就是不方便对文件进行更改，只适用于固定不变数据文件。但是在这个时代，不变的东西还真不多了呢。读者可以根据自己需求选择使用哪种方法。云存储的具体使用方法我在这也就不多说了，想了解的可以网上自行搜索一下。

好了，今天的文章就到此为止。怎么样，学习是不是使你感到快乐呢？

---

**扫描二维码**，关注我们哟

![img](.\Excel-VLOOKUP函数的进阶使用.src.image\aHR0cHM6Ly9tbWJpei5xcGljLmNuL21tYml6X2pwZy94aHdIaWFRUVcyZ3NuSVlRYzhCQndVNmNTRmRyYm1mMzh3YnBkeWRURE1Zb1M3aFBrQVhaVm0wWXJ5aWN4WkhkYXlvNlR1VDR0MEZsQjZEZ0RpYko4dEVkUS82NDA.jfif)



{docsify-updated}