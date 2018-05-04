## CSS 规范
- CSS规则声明
	- 把一个选择器 | 一组属性称为 “规则声明”
	- 规则声明中，“选择器” 选取 DOM元素，选择器可以是 class, element, attribute等
		* 不推荐使用 id选择器
	- 属性以 ` key: value; `键值对形式存在，一个规则声明包含一个或多个属性
	```
	// 规则声明
	.card { // 选择器
		font-size: 16px; // 属性
		height: 50px;
	}

	[role="card"] {
		background-color: #09f;
	}
	```

- 2个空格缩进
- 不要使用 id 选择器
	- ID选择器的优先级为最高，且 ID选择器不能重用
	- 处理样式优先级 https://csswizardry.com/2014/07/hacks-for-dealing-with-specificity

- 在选择器的 { 左花括号前加上一个空格
- : 属性的后面加上一个空格，前面不加空格
- 规则声明的右花括号 } 独占一行
- 在一个规则声明多个选择器，每个选择器独占一行
- 每个规则声明之间用空行分割

- 使用中划线 - 代替 驼峰命名法，如果使用 REM，推荐用 下划线 _
	- BEM参考 OOCSS & BEM

- 边框
	- 定义无边框样式时，使用 0 代替 none

- 注释
	- 使用 行注释 代替 块注释，Sass中是 //
	- 注释单独占一行，避免行尾注释
	- 给没有自注释的代码写上详细说明，比如
		* 为什么用到 ` z-index `
		* 兼容性处理 | 针对特定浏览器的 hack

- JavaScript 钩子类
	- 用特定的 JS类名时，添加 ` .js- ` 前缀，避免 CSS&JS绑定相同的类，避免耦合
	- ` <button class="btn js-submit">提交</button> `

规范的用法
```
.avatar {
	border-radius: 50%;
	border: 0;
}

.one,
.two,
.three {
	width: 100%;
	height: 100%;
}
```

不规范的用法
```
.avatar{
	border-radius: 50%;
	border: none; }
.one, .two, .three {
	width: 100%;
}
#logo{
	//...
}
```
- 参考资料 Airbnb CSS | SASS指南 https://github.com/airbnb/css
- BEM参考资料 https://www.zhihu.com/question/21935157


## CSS规范 - OOCSS & BEM
- OOCSS是什么？
	- Object Oriented CSS 面向对象的CSS
	- 不是新语言或者是新的CSS框架，就是一种 CSS写法，一种容易重用的CSS规则
	- OOCSS思想就是：鼓励你把样式表看作“对象”的集合：
		* 创建可重用性、可重复性的代码段
		* 让你可以在整个网站中多次使用
	- OOCSS核心：就是用最简单的方式编写最整洁，最于净的CSS代码，
		- 从而使代码更具重用性，可维护性和可扩展性

- OOCSS的原则
	- 独立的结构和样式
	- 独立的容器和内容

- BEM是什么？
	- BEM的意思就是块（block）、元素（element）、修饰符（modifier）
	- BEM 最多只有 B+E+M 三级
	- BEM可以作为一套遵循 OOCSS 的参考指导规范
		* Block !误区: 这个block并非inline-block里的block
		* 而是将所有东西都划分为一个独立的模块, block可以相互嵌套
			* 一个header是block,
			* header里嵌套的搜索框是block
			* 甚至一个icon一个logo也是block

- BEM的优势：
	- 理清 CSS和HTML之间清晰且严谨的关系
	- 减少嵌套，降低特定性
	- 创建出可扩展的样式表
		* 可重用，易组合的组件

BEM 案例
```
.card {}          一个块 Block，表示高层次的组件
.card-title {}    一个元素 Element，属于 .card的一部分，块是有元素组成的
.card-content {}  一个元素 element
.card-featured {} 一个修饰符 Modifier，表示这个块与 .card 有着不同的状态或变化

<section class="card card-featured">
	<h1 class="card-title">标题</h1>
	<div class="card-content">
		//...
	</div>
</section>
```


## CSS规范 - Sass
- 使用 ` .scss ` ，不要用 ` .sass `的语法
- 永远不要嵌套 ID选择器
	```
	.card{
		.content{
			.profile{
				// STOP!
			}
		}
	}
	```
- 属性声明的顺序
	- 先列出除了 ` @include `和嵌套选择器之外的所有属性声明
	- 紧随其后的是 ` @include `和嵌套选择器，这样阅读性更高
	- 把嵌套选择器放到最后，规则声明和嵌套选择器之间要用空行分割
		* 嵌套规范也要遵守CSS的规范
		* 嵌套选择器不要超过 3层
	```
	.btn {
		background-color: #90f;
		font-weight: 700;
		@include transition(background .5s ease);

		.inner {
			font-size: 12px;
		}
	}
	```

- @mixin 增强清晰性 | 抽象化
	- 命名良好的函数

- @extend
	- 避免使用 ` @extend `继承
	- 因为不直观，有潜在风险，如加载顺序变化和样式的覆盖

- 变量名使用 中划线 - 代替 驼峰命名法
	- 仅用在当前文件的变量，在变量前添加下划线
	```
	$my-name 代替 $myName
	
	$_name 当前文件内的变量
	```



## CSS3 工具
1. http://westciv.com/tools/gradients 渐变效果
	- 生成背景渐变、阴影、旋转和边框圆角效果

2. http://www.colorzilla.com/gradient-editor 渐变
	- 类似 Photoshop 中的渐变功能

3. http://csswarp.eleqtriq.com 文字路径
	- 文本旋转效果的代码，应用了 CSS3 旋转特性

4. http://www.css3maker.com/css3-animation.html css3 动画
	- 渐变、阴影、旋转、动画等效果，并生成对应代码



## CSS3 参考资料
- https://github.com/chokcoco/iCSS