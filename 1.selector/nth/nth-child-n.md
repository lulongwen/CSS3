# 结构伪类元素
	:nth-child(n)
	:nth-last-child(n)
	:nth-of-type(n)
	:nth-last-of-type(n)

参数n可以是整数（1、2、3、4）、关键字（odd、even），还可以是公式（2n+1、-n+5），但参数n的起始值始终是1，而不是0。换句话说，当参数n的值为0时，选择器将选择不到任何匹配的元素。

1 :nth-child(3)”将选择一个系列中的第3个元素。
2 :nth-child(2n)
		n=0时，2×0=0，不选中任何元素；
		n=1时，2×1=2，选中系列中的第2个元素；
		n=2时，2×2=4，选中系列中的第4个元素；
		n=3时，2×3=6，选中系列中的第6个元素；

3 参数n为表达式“n+length”
		选择大于或等于length的元素，例如“:nth-child(n+3)”。
		n=0时，0+3=3，选中系列中的第3个元素；
		n=1时，1+3=4，选中系列中的第4个元素；
		n=2时，2+3=5，选中系列中的第5个元素；
		n=3时，3+3=6，选中系列中的第6个元素；

4 其中b是您想设置的偏移值，其表示隔length个元素选中第n*length+b个元素，
例如“:nth-child(2n+1)”。
		n=0时，2×0+1=1，选中系列中的第1个元素；
		n=1时，2×1+1=3，选中系列中的第3个元素；
		n=2时，2×2+1=5，选中系列中的第5个元素；
		n=3时，3×2+1=7，选中系列中的第7个元素；