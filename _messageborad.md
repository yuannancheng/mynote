<!-- 留言板 -->

<script>
// 清除侧边栏，导航栏
var remove = ['app-nav', 'github-corner', 'cover', 'sidebar-toggle', 'sidebar'];
var removeEl = '';
remove.forEach((e, i) => {
    removeEl += '.' + e;
    if (i != remove.length - 1){
    	removeEl += ', ';
	}
});
style = document.createElement("style");
style.innerHTML = ( removeEl + "{display:none}");
document.head.appendChild(style);
window.onload = () => {
    remove.forEach((e) => {
        var el = document.getElementsByClassName(e)[0];
        el.remove();
    });
}
</script>




# 留言板

---



最近较忙，有事可以给我 [打电话](tel:17870181601 "Call me up") 或者 [发邮件](mailto:y17870181601@163.com "Email me")。



{docsify-updated}