# Fleet
Fleet 能够帮助你快速构建页面，让你只需要专注页面UI设计和数据请求即可。

> Fleet 是心血来潮下的作品，不适用于生产环境。只应该被用于大学生应付小组作业。

## 安装

```
npm i fleetjs
```



## 使用教程

引入 fleet.css 和 fleet.js 

```html
<link rel="stylesheet" href="node_modules/fleetjs/dist/css/fleet.css">
```

```html
<script src="node_modules/fleetjs/dist/fleet.js"></script>
```



### Fleet何如工作？

一个例子搞懂Fleet 如何工作。

```html
<div class="box" fl="useFleet">
  <p :title="hello" $="showText">Fleet 使用。</p>
  <button @click="changeTitle">点我</button>
</div>
```

```javascript
class UseTest extends Fleet {
  $init() {
    this.data = {
      hello: "Fleet之属性绑定"
    };
  }

  changeTitle(e) {
    const p = this.$showText;
    const btn = e.target;

    console.log(p, btn);

    this.data.hello = "hello发生了改变……";
  }
}

const test = new UseTest("useFleet");
console.log(test);
```


如上所示，

`fl` 为标记Fleet的作用域。

`:` 为属性绑定。其作用与vue类似。

`@` 为函数绑定。其作用与vue类似。所引用函数的`this`指向为Fleet 的示例。

`$` 为元素标记符。标记的元素都会加载都Fleet的示例上，并以`$`符为开头。

实现了Fleet的示例 `UseTest` 通过`$init()` 方法初始化`data`数据。
