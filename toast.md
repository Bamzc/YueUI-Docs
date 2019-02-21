
## 消息提示C-toast

常用于主动操作后的反馈提示

### 基础用法

从中间出现，默认1.5秒后关闭

:::配置属性options，见文末
:::

```html
<template>
	<div>
		<button @click="testToast1">toast简便用法</button>
		<button @click="testToast2">toast标准用法</button>
	</div>
</template>
<script>
	export default {
		data () {},
		methods: {
			testToast1 () {
				this.$toast('我是toast1')
			}
			testToast2 () {
				this.$toast({
					message: '我是toast2',
					duration: 1500,
					callback () {
						console.log('执行完毕')
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
		<button @click="testToast1">成功</button>
		<button @click="testToast2">警告</button>
		<button @click="testToast3">错误</button>
	</div>
</template>
<script>
	export default {
		data () {},
		methods: {
			testToast1 () {
				this.$toast({
					message: '我是toast1',
					duration: 1500,
					iconClass: 'success',
					callback () {
						console.log('执行完毕')
					}
				})
			},
			testToast2 () {
				this.$toast({
					message: '我是toast2',
					duration: 1500,
					iconClass: 'warning',
					callback () {
						console.log('执行完毕')
					}
				})
			},
			testToast2 () {
				this.$toast({
					message: '我是toast3',
					duration: 1500,
					iconClass: 'error',
					callback () {
						console.log('执行完毕')
					}
				})
			}
		}
	}
</script>
```
### 全局方法

YueUI 为 Vue.prototype 添加了全局方法 $toast。因此在 vue instance 中可以采用本页面中的方式调用 `toast`。

### 单独引用

单独引入 `toast`：

```javascript
import { Toast } from 'yue-ui';
```
### Options
| 参数      | 说明          | 类型      | 可选值                           | 默认值  |
|---------- |-------------- |---------- |--------------------------------  |-------- |
| message | 消息文字 | string | — | — |
| iconClass | 自定义图标的类名，会覆盖 `type` | string | — | — |
| customClass | 自定义类名 | string | — | — |
| duration | 显示时间, 毫秒。| number | — | 3000 |
### 方法
调用 `toast` 或 `this.$message` 会返回当前 Toast 的实例。如果需要手动关闭实例，可以调用它的 `close` 方法。
| 方法名 | 说明 |
| ---- | ---- |
| close | 关闭当前的 toast |