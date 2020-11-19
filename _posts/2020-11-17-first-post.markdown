---
layout: post
title:  鍵盤事件的比較(keydown/keyup/keypress)
date:   2020-11-17 11:19:41 +0800
categories: jekyll update
---
Java Script Web Programming 上課筆記 2020-11-17

在 Java Script 裡的 "keydown/keyup" 和 "keypress" 有什麼差別呢? 

首先，要先了解 "key" 跟 "character" 是什麼。"key" 是電腦鍵盤上實際的每個按鍵，而 "character" 是按下按鍵產生的符號。"keydown/keyup" 事件分別代表按鍵(keys)被按下和放開的瞬間，而 "keypress" 代表一個符號(charater)被打出來。
意思是說，前者對任何按鍵都有作用(例如shift, control等沒有符號的按鍵)，後者則是只針對有符號的按鍵(包含字母及標點符號等)。

*實際操作在不同瀏覽器可能有不同效果

以下紀錄三種鍵盤事件(keydown/keyup/keypress)的觸發作用

{% highlight ruby %}
function keyFunction(e){
	e = e || window.event;
	if (e.type=="keydown") {
		numDown++;
        document.getElementById('btnDown').value = "Key Down (" + numDown + ")";
	} else if (e.type=="keypress") {
		numPress++;
        document.getElementById('btnPress').value = "Key Pressed (" + numPress + ")";
	} else { // keyup
		numUp++;
		document.getElementById('btnUp').value = "Key Up (" + numUp + ")";
	}
    document.getElementById('txtKeyin').value = "";
    document.getElementById('txtKeyin').focus();
	return (e.keyCode != 13);
}
{% endhighlight %}