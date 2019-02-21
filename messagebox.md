
## Message 弹窗提示

弹窗提示

### 基础用法

从中间出现

***配置属性options，见文末***

```html
<template>
<div>
	<button @click="messageBox1">messageBox简便用法</button>
	<button @click="messageBox2">messageBox标准用法</button>
</div>
</template>
<script>
export default {
	data () {},
	methods: {
		messageBox1 () {
			this.$messagebox('提示', '陈超超也是大傻叉', (y) => {
				console.log(y)
			})
		}
		messageBox2 () {
			this.$messagebox({
				title: '提示',
				content:'陈超超也是大傻叉',
				showCancel: true,
				callback (y) {
					console.error(y)
				}
			})
		}
	}
}
</script>
```
### 不同状态

用来显示「成功、警告、错误」类的操作反馈。
```html
<template>
<div>
	<button @click="messagebox1">成功</button>
	<button @click="messagebox2">警告</button>
	<button @click="messagebox3">错误</button>
</div>
</template>
<script>
export default {
	data () {},
	methods: {
		messagebox1 () {
			this.$messagebox({
				content:'陈超超也是大傻叉',
				iconClass: 'success',
				showCancel: true,
				callback (y) {
					console.error(y)
				}
			})
		},
		messagebox2 () {
			this.$messagebox({
				content:'陈超超也是大傻叉',
				iconClass: 'warning',
				showCancel: true,
				callback (y) {
					console.error(y)
				}
			})
		},
		messagebox3 () {
			this.$messagebox({
				content:'陈超超也是大傻叉',
				iconClass: 'error',
				showCancel: true,
				callback (y) {
					console.error(y)
				}
			})
		}
	}
}
</script>
```
### 全局方法

YueUI 为 Vue.prototype 添加了全局方法 $message。因此在 vue instance 中可以采用本页面中的方式调用 `message`。

### 单独引用

单独引入 `message`：
```javascript
import { MessageBox } from 'yue-ui';
```
此时调用方法为 `$message(options)`。

### Options
| 参数      | 说明          | 类型      | 可选值                           | 默认值  |
|---------- |-------------- |---------- |--------------------------------  |-------- |
| title | 标题文字, 此属性与iconClass属性不共存 | string | — | — |
| content | 消息文字 | string | — | — |
| iconClass | 自定义图标的类名，会覆盖 `type` | string | — | — |
| showCancel | 是否显示关闭按钮 | boolean | — | false |
| callback | 点击按钮时的回调函数, 参数为被关闭的 message 实例 | function | — | — |
