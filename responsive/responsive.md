# 响应式设计
* Responsive Web Design 指可以自动识别屏幕宽度,并做出相应调整的网页设计


## viewport
* viewport 的分类
	* layout viewport 
	* visual viewport

* 通俗的讲，移动设备上的viewport就是设备的屏幕上能用来显示我们网页的那一块区域
* 再具体一点，就是浏览器上(也可能是一个app中的webview)用来显示网页的那部分区域.
* 但viewport又不局限于浏览器可视区域的大小，它可能比浏览器的可视区域要大，也可能比浏览器的可视区域要小。
* 移动设备上的浏览器都会把自己默认的viewport设为980px或1024px

```
<meta
	name="viewport"
	content="width=device-width,
	user-scalable=no,
	initial-scale=1.0,
	maximum-scale=1.0,
	minimum-scale=1.0">


```



## DPI
* iphone3 分辨率为320x480
* iphone4 分辨率为640x960
* 但是两款手机的实际宽度都是320px的，这样就导致了屏幕尺寸没变化，像素却多了一倍
* 这时，一个css像素是等于两个物理像素的，window.devicePixelRatio检测的结果是2

```
	检测 DPI
		window.devicePixelRatio

	DPI适配技巧
  	准备多张图	xxx.png  xxx@2x.png  xxx@3x.png

  	iconfont
  	svg

```



## @media

```
	<link type="text/css" rel="stylesheet" href="phone.css" media="screen"/>

	@media all and (min-width: 321px) and (max-width: 640px) {
    body {
      font-size: 20px;
    }
  }




```


## Media Type 媒体类型
```
	all    所有设备
  screen 所有的屏幕设备
  print  打印机设备

```


## Media Query
```
	width
	height
  device-width
  device-height

  device-pixel-ratio
  orientation 检测横竖屏
  	landscape 横屏
  	portrait  竖屏


```