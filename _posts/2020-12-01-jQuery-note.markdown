---
layout: post
title:  jQuery Note - 風琴式功能表
date:   2020-12-01 11:03:15 +0800
categories: jekyll update
---
Java Script Web Programming 上課筆記 2020-12-01

主功能表-catalog

子功能表-item

一開始設定item都隱藏(.hide())，只能看到catalog

當某個catalog被按下(.click())，就讓item秀出來(.item:visible)並慢慢展開(.slideUp('slow'))

{% highlight ruby %}
$(document).ready(function() {
   $('.item').hide();
   $('.item:first').show();
   //$('.item').not(':first').hide();
   $('.catalog:first').addClass('active'); 
   $('.catalog').click(function() {
      $('.item:visible').slideUp('slow').prev().removeClass('active');
      $(this).addClass('active').next().slideDown('slow');
   });
});
{% endhighlight %}

-在最前面加入style設定css

    記得先include jQuery
	
	<script src="http://code.jquery.com/jquery-1.8.3.min.js"></script>

-在body裡面放div排版

{% highlight ruby %}
<div id="accordion"> 
	<div class="catalog"> 
		<h4>程式語言</h4>
	</div>          
	<ul class="item"> 
		<li><a href=''>Java</a></li> 
		<li><a href=''>Visual Basic</a></li> 
		<li><a href=''>Visual C++</a></li> 
	</ul>
	<div class="catalog"> 
		<h4>網頁設計</h4>
	</div>          
	<ul class="item"> 
		<li><a href=''>ASP.NET</a></li> 
		<li><a href=''>PHP</a></li> 
		<li><a href=''>JSP</a></li> 
	</ul>
	<div class="catalog"> 
		<h4>資料庫系統</h4>
	</div> 
	<ul class="item"> 
		<li><a href=''>SQL Server</a></li> 
		<li><a href=''>Oracle</a></li> 
		<li><a href=''>MySQL</a></li> 
	</ul>  
</div>  
{% endhighlight %}