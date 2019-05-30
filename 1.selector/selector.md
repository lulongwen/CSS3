# CSS3选择器
> 让某个样式应用于特定的HTML元素，首先要找到该元素，执行这个任务的规则就是 CSS选择器
* 选择器的性能和优先级
	* id > class > element > attribute



## 1 基本选择器
* 浏览器全部兼容
	
```
	* 通配选择器
	E  元素选择器
	#id  ID选择器
	.class 类选择器
	selector1, selectorN  群组选择器


	width: calc(100% - 30px);

```
		



## 2 层次选择器
* 浏览器兼容 IE 7+
	E F    后代选择器 （包含选择器）
	E > F  子选择器
	E + F  相邻兄弟选择器
	E ~ F  通用兄弟选择器
		



## 3 动态伪类选择器
		伪类选择器 都以英文冒号开始 :
	E:link
	E:visited
	E:active  IE8+
	E:hover   IE6仅支持 a:hover
	E:focus   IE8+
		LoVe / HAte ，锚点伪类必须遵守 爱恨原则（link - visited - hover - active）



## 4 目标伪类选择器
	:target
		浏览器兼容： IE9+



## 5 语言伪类选择器
	E:lang
		<html lang="zh-CN">
			:lang(en){ background:#ccc }
			:lang(fr){ quote: '<' '>'; }
		浏览器兼容 IE8+



## 6 UI状态伪类选择器
	E:checked 选中状态
	E:enabled 启用状态
	E:disabled 禁用状态
		浏览器兼容 IE 9+



## 7 结构伪类选择器
	E:first-child 父元素的第一个子元素 等于 E:nth-child(1)
	E:last-child  父元素的最后一个子元素 等于 E:nth-last-child(1)
	E:root  文档根元素，HTML中，根元素始终是 html
	E F:nth-child(n) 
		n可以是
			整数（1、2、3）
			关键词（even、odd）
			公式（ 2n+1、 -n+5、5n、2*5+b、n+5 ），n的起始值为 1，不是 0

	E F:nth-last-child(n) 倒数第 n 个子元素 ，:nth-last-child(1) 选择的始终是最后一个元素
	E:nth-of-type(n)      指定类型的第 n 个子元素
	E:nth-last-of-type(n) 指定类型的倒数第 n 个子元素

	E:first-of-type  指定类型的第一个子元素，等价于nth-of-type(1) 
	E:last-of-type   指定类型的最后一个子元素，等价于nth-last-of-type(1)

	E:only-child  只包含一个子元素
	E:only-of-type 只包含一个指定类型的子元素
	E:empty 没有任何内容，该元素不包括任何节点，哪怕是一个空格
		浏览器支持 IE9+



## 8 否定伪类选择器
	:not()
		li:hover a:not(:hover){ opacity: .6 }
		浏览器支持 IE 9+



## 9 伪元素选择器
	::before 元素之前插入
	::after 元素之后插入 （插入内容不会成为DOM的一部分）
	::before & ::after 清除浮动、字体图标
	::first-letter 第一个字母
	::first-line 第一行
	::selection  （鼠标）选中突出显示



## 10 属性选择器
	E[attr] 属性  , a[id]
	E[attr = val]   属性值为val , a[id=title]
		a[id= box][title] {color:#0ff}
		a[class="link item show"] {color:#0ff}

	E[attr |= val]  属性值以 val 或 val- 开始 , a[id |= title]
	E[attr ~= val]  多个属性值（attr属性值）有多个空格分隔，其中一个值为 val ,
					a[id ~= title]
	E[attr *= val]  通配* 任意位置有 val 值的 , a[class *= title]
	E[attr ^= val]  属性值以 val 开始
		a[class ^= title]
		a[href ^= http://]
		a[href ^= mailto]

	E[attr $= val]  属性值以 val 结束的
		a[http $= png]
		a[href $= doc]
		a[href $= ppt]
		a[href $= xls]
		a[href $= zip], a[href $= rar]

		^  开始
		$  结束
		|  包含 或 val-
		~  多个属性值，其中一个值为 val
		* 通配
			浏览器兼容：IE 7+

















【伪类选择器】
链接
	:link
	:visited

用户动作 
	:hover 
	:active
	:focus

目标 :target

:checked
:enabled
:disabled
:selection
:root


用户界面 :disabled
	选择所有禁用的 input 和 button 元素,disabled 属性规定应该禁用 input 元素
	disabled 属性无法与 <input type="hidden"> 一起使用
	被禁用的 input 元素既不可用，也不可点击。可以设置 disabled 属性，直到满足某些其他的条件为止（比如选择了一个复选框等等）。然后，就需要通过 JavaScript 来删除 disabled 值，将 input 元素的值切换为可用。


结构伪类
	:nth-child(1)
	:nth-child(odd)  /* 奇数选择器 */
	:nth-child(even) /* 偶数选择器 */

	:nth-child(*n+b) /* 倍数选择器 */
	序号写法：
li:nth-child(3){background:orange;}/*把第3个LI的背景设为橙色*/
 
倍数写法：
li:nth-child(3n){background:orange;}/*把第3、第6、第9、…、所有3的倍数的LI的背景设为橙色*/
 
倍数分组匹配：
li:nth-child(3n+1){background:orange;}/*匹配第1、第4、第7、…、每3个为一组的第1个LI*/
li:nth-child(3n+5){background:orange;}/*匹配第5、第8、第11、…、从第5个开始每3个为一组的第1个LI*/
li:nth-child(5n-1){background:orange;}/*匹配第5-1=4、第10-1=9、…、第5的倍数减1个LI*/


	:nth-last-child(1)
	:nth-last-child(odd)
	:nth-last-child(even)



	:nth-of-type()
	:nth-last-of-type()

第一个元素
	:first-child
	:nth-child(1)
	:last-child


	:first-of-type()
	:last-of-type()

独生子  :only-child


空白元素  :empty()


否定，反选  :not()
	:not('enen')
	:not('odd')
	:not('.box')
	:not('span')
原生的 JavaScript 函数
$('li').not(document.getElementById('notli')).css('background-color', 'red');


选择每个元素的首行与首字
	:first-line
	:first-letter

之前与之后
	:before 
	:after


后代
	div img

儿子
	div>img

兄弟
	h1+h2 选择的是h2

【通配符选择器 】
	*{margin:0;padding:0;}