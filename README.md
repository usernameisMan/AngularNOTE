# AngularNOTE

ng-app 属性 标记了angular 脚本的作用域范围

#绑定
```html
<p> here {{1 + 1}}</p>
```
这个绑定告诉AngularJS需要运算其中的表达式并将结果插入DOM中


#组件
```js
//模块文件
angular.module('phonecatApp', []);
//组件文件
angular.
  module('phonecatApp').
    component('greetUser', {
    template: 'Hello, {{$ctrl.user}}!',
    controller: function GreetUserController() {
      this.user = 'world';
    }
    });
```
创建一个组件,每次我们使用
 ```js
<greet-user></greet-user>
```
在视图的时候，AngularJS将它扩展成一个DOM子树，使用提供template和管理的指定控制器的实例构造。
我们的greetUser是可重用的。只需<greet-user></greet-user>在页面中的任何地方，以获得greetUser。
我们的主视图（）是更清洁和更声明。只要看看它，我们知道有一个手机列表。我们不打扰实现细节。index.html
我们的组件是隔离和安全的“外部影响”。同样，我们不必担心，我们可能会意外破坏应用程序的其他部分。我们的组件内部发生了什么，停留在组件内部。
更容易孤立地测试我们的组件。
https://docs.angularjs.org/img/tutorial/tutorial_03.png具体描述
#过滤器

```js
Search: <input ng-model="$ctrl.query" />

<li ng-repeat="phone in $ctrl.phones | filter:$ctrl.query">
  <span>{{phone.name}}</span>
  <p>{{phone.snippet}}</p>
</li>
```
AngularJS将输入框的值绑定到指定的数据模型变量，ngModel并保持两者同步。
用户输入到输入框（绑定到）的数据立即可用作列表中继器（）中的过滤器输入。当对数据模型的更改导致中继器的输入改变时，中继器有效地更新DOM以反映模型的当前状态
