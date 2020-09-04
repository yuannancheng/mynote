<!-- 设置 -->



# 设置

---

## 主题色

<br>

<div id="theme-color-box"></div>

<script>
	var theme = {
        '绿色' : '#42b983',
        '蓝色' : '#4ea1db',
        '红色' : '#ca0c16',
        '黑色' : '#000'
    }
    var el = document.getElementById('theme-color-box');
    for (var key in theme){
        var span = document.createElement('span');
        span.setAttribute('onclick', '_changeThemeColor(\'' + theme[key] + '\');');
        span.style.position = 'relative';
        span.style.border = '1px solid ' + theme[key];
        // span.style.borderRadius = '5px';
        span.style.display = 'inline-block';
        span.style.margin = '10px';
        span.style.padding = '10px 20px';
        //span.style.height = '40px';
        span.style.color = theme[key];
        span.style.textAlign = 'center';
        span.style.verticalAlign = 'middle';
        span.style.cursor = 'pointer';
        span.innerText = key;
        el.append(span);
    }
    var span = document.createElement('span');
    span.setAttribute('onclick', 'var input = prompt(`输入您想要的色码，请使用以下格式中的任意一种。\n    1、颜色名，如：skyblue\n    2、16进制色码\n    3、RGB色码\n    4、HSL色码`,"");if(input){_changeThemeColor(input);}');
    span.style.position = 'relative';
    span.style.border = '1px solid transparent';
    span.style.borderImage = 'linear-gradient(to bottom right, red, blue) 1';
    span.style.borderRadius = '5px';
    span.style.display = 'inline-block';
    span.style.margin = '10px';
    span.style.padding = '10px 20px';
    span.style.backgroundImage = 'linear-gradient(to bottom right, red, blue) 1';
    span.style.webkitBackgroundClip = 'text';
    span.style.textAlign = 'center';
    span.style.verticalAlign = 'middle';
    span.style.cursor = 'pointer';
    span.innerText = '自定义';
    el.append(span);
</script>


## 缓存

<a href="javascript:location.reload(true);">强制刷新</a>