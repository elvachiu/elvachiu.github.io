---
layout: post
title:  My Notes for learning Angular
date:   2020-12-22 09:56:13 +0800
categories: jekyll update
---
Java Script Web Programming 上課筆記 2020-12-22

用 Angular JS 處理前端

在 div 裡面寫 ng-app="myApp" ng-controller="customersCtrl"

{% highlight ruby %}
<table>
  <tr ng-repeat="x in names">
    <td>{{ x.Name }}</td>
    <td>{{ x.Country }}</td>
  </tr>
</table>
{% endhighlight %}

