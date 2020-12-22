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

ng-repeat 有點像for loop，寫一個<tr>，後面會依據資料數量x跑出對應列數

{% highlight ruby %}
<script>
var app = angular.module('myApp', []);
app.controller('customersCtrl', function($scope, $http) {
    $http.get("customers.php")
    .then(function (response) {$scope.names = response.data.records;});
});
</script>
{% endhighlight %}

拿records的資料放到scope ($scope.names = response.data.records;) 就能取的想要放進table的資料了

{% highlight ruby %}
<select ng-model="selectedName" ng-options="x for x in names">
</select>
{% endhighlight %}

另外，ng-options也有類似功能，可以做一個dropdown list