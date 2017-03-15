# AngularNOTE

ng-app 属性 标记了angular 脚本的作用域范围

#绑定
```html
<p> here {{1 + 1}}</p>
```
这个绑定告诉AngularJS需要运算其中的表达式并将结果插入DOM中


#组件
```js
component('greetUser', {
  template: 'Hello, {{$ctrl.user}}!',
  controller: function GreetUserController() {
    this.user = 'world';
  }
```
创建一个组件,每次我们使用
 ```js
<greet-user></greet-user>
```
在视图的时候，AngularJS将它扩展成一个DOM子树，使用提供template和管理的指定控制器的实例构造。
