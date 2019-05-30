# viewport 视口
* PC端视口就是浏览器可视区域
* 可视视口，默认就是手机屏幕的宽度

```

	ie=edge 表示强制以最新的IE浏览器模式渲染页面
  <meta http-equiv="X-UA-Compatible" content="ie=edge">


<meta name="viewport" content="" />
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">

	width [ pixel_value | device-width ] 视口宽度
		width 直接去设置具体数值大部分的安卓手机是不支持的，但是IOS 是支持的

	height 视口高度
	device-width  设备屏幕的宽度
	device-height 设备屏幕的高度
	orientation   横向还是纵向

	resolution 检测屏幕或打印机的分辨率


	user-scalable 是否允许用户缩放页面 （ no || yes ）
	initial-scale 初始化比例
	minimun-scale 允许缩放的最小比例
	maximun-scale 允许缩放的最大比例

	min-resolution: 300dpi
		aspect-ratio: 基于视口宽度和高度的宽高比
		width/height 如：16/9, 4/3

	device-aspect-ratio: 设备屏幕的宽度，渲染表面的宽度
	color: 每种颜色的位数 
	bits 如min-color:16位,8位

	target-densitydpi
		dpi_value  取值在70-400 //每英寸像素 ，IOS不支持，大部分安卓支持
		device-dpi 设备默认的像素密度
		high-dpi 高像素密度
		medium-dpi 中等像素密度
		low-dpi    低像素密度
		webkit 内核已不准备在支持这个特性了



媒体查询 media
<link rel="stylesheet" href="" media="screen and(min-width:600px)">

@import url('css/index.css') all and (min-width:600px);

@media all and (min-width:600px){
	.box{ width:1000px; }
}

一 媒体类型
	all 所有媒体
	braille 盲文触觉设备
	embossed 盲文打印机
	print 手持设备
	projection 打印预览
	screen 彩屏（屏幕）设备
	speech 听觉类似的媒体设备
	tty 不适用于像素的设备
	tv 电视

二 媒体特性
	(max-width:599px)  max-width 最大的宽度
	(min-width:600px)  min-width 最小的宽度
	(orientation:portrait)   竖屏
	(orientation:landscape)  横屏
	(-webkit-min-device-pixel-ratio:2) 像素比

三 关键字
	and
	not  用来排除某种特定的媒体类型
	only 用来指定特定的媒体类型
			很多时候用来对那些不支持媒体特性却支持媒体类型的设备


@media all and(orientation:landscape){
	//横屏
}

@media screen and (orientation;portrait){
	//竖屏
}

