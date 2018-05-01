## em 相对长度单位
	1.em 相对参照物为 父元素的font-size
	2.em 具有继承的特点
	3.当没有设置font-size时，浏览器会有一个默认的em设置
		1em = 16px;

	em的缺点：容易混乱


## rem
rem的相对参照物为根元素(root) html；相对参照固定不变，所以比较好计算

当没有设置font-size时，浏览器会有一个默认的rem设置，**1rem = 16px**，这点与em是一致的。

	font-size:62.5%
		1rem = 10px ( 10/16 *100% )

	font-size:100%
		1rem = 16px
