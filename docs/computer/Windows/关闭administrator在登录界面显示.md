# 关闭administrator在登录界面显示

---

```shengming
声明：技术造福人类，禁止用于非法用途，如有其它非法用途造成损失，和本篇无关。
```

1. Win键+R键打开运行bai窗口，输入`regedit`，点击确定。
2. 定位到`HKEY_LOCAL_MACHING\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon`
3. 新建`\SpecialAccounts\UserList`节点，并在UserList这个节点下新建一个`DWORD 32位`的值 ，键名设置为administrator，值设为 0；
4. 关闭编辑器，重启即可。



转载自[@泡影果果616](https://zhidao.baidu.com/hangjia/profile?uid=4d574069236f25705e79026a)在百度知道的[回答](https://zhidao.baidu.com/question/360615908.html)。



{docsify-updated}