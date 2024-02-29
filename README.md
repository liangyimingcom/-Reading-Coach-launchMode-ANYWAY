``` javascript
// ==UserScript==
// @name        Reading Coach launchMode ANYWAY
// @namespace   Violentmonkey Scripts
// @match       https://coach.microsoft.com/*
// @grant       none
// @version     5.0
// @author      -
// @description 2/29/2024, 10:12:43 PM
// ==/UserScript==

window.onload = function() {
    // 创建一个新的按钮元素
    var button1 = document.createElement('button');
    button1.textContent = 'Update launchMode=normal';
    button1.style.position = 'fixed';
    button1.style.top = '10px';
    button1.style.right = '10px';
    button1.style.zIndex = 10000; // 使按钮显示在其他元素之上

    // 当按钮被点击时，修改所有链接的 href 属性
    button1.onclick = function() {
        // 获取页面上所有的 iframe
        var iframes = document.querySelectorAll('iframe');

        // 遍历所有的 iframe
        iframes.forEach(function(iframe) {
            // 检查 iframe 的 src 属性是否包含 'launchMode=reading'
            if (iframe.src.includes('launchMode=reading')) {
                // 如果包含，将 'launchMode=reading' 替换为 'launchMode=normal'
                iframe.src = iframe.src.replace('launchMode=reading', 'launchMode=normal');
            }
        });
    };

      // 创建一个新的按钮元素
    var button2 = document.createElement('button');
    button2.textContent = 'Update launchMode=reading';
    button2.style.position = 'fixed';
    button2.style.top = '10px';
    button2.style.left = '10px';
    button2.style.zIndex = 10000; // 使按钮显示在其他元素之上

    // 当按钮被点击时，修改所有链接的 href 属性
    button2.onclick = function() {
        // 获取页面上所有的 iframe
        var iframes = document.querySelectorAll('iframe');

        // 遍历所有的 iframe
        iframes.forEach(function(iframe) {
            // 检查 iframe 的 src 属性是否包含 'launchMode=reading'
            if (iframe.src.includes('launchMode=normal')) {
                // 如果包含，将 'launchMode=reading' 替换为 'launchMode=normal'
                iframe.src = iframe.src.replace('launchMode=normal', 'launchMode=reading');
            }
        });
    };


    // 将按钮添加到页面上
    document.body.appendChild(button1);
    document.body.appendChild(button2);
};



```

