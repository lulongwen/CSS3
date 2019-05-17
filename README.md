# CSS3核心知识点

## CSS进阶顺序
1. 基础
  * 能还原设计稿、兼容各种主流浏览器
  * 盒子模型、浮动、定位

2. 进阶
  * CSS 分层架构、CSS3 、响应式、预处理
  * 圆角、动画、个性边框、媒体查询
  * 固定布局、流式布局、响应式布局
  * 适应移动设备的发展
  

## Css 规范
### Reset.css样式重置
  * normalize.css
  * rebot.css

### Css规范
### Css hack兼容性
```
<<<<<<< HEAD
  Css 选择器
  Css 盒模型
  Flex 弹性盒模型

  @media 媒体查询
  Gradient 渐变
  Animation 动画
  Iconfont 字体图标

  Less
  Sass
    很多项目和工作中会用到，一定要掌握

  Css 规范
    Reset.css 样式重置
    Css 规范
    Css hack css兼容性

  Css 网页布局
    Flex
    定位布局 position: absolute
    流式布局 Media Query
    Column 多栏布局
    inline-block 布局
    栅格系统

  Css3 工具
```


=======
  reset.css + variable.css + font.css + layout.css
  csshack.css
>>>>>>> sass

```



## Css 选择器
  * 标签选择器 div
  * 类选择器 .box
  * id 选择器 #box
  * 通配符选择器 *
  * 子元素选择器 body > div
  * 后代选择器 body ~ div
  * 相邻选择器 body + div
  * 属性选择器 a[href=""]
  * 复合选择器 a, b {}
  * 伪类选择器
  * 结构化伪类选择器
  * 目标伪类选择器 target
  * 状态伪类选择器
  * 否定伪类选择器 not(select)

## Css 盒模型

## Flex 弹性盒模型

## Css 网页布局
### Flex弹性盒模型
  * 控制盒子方向
  * 对齐方式
  * 显示顺序
  * 弹性盒模型设计阅读 APP

### 定位布局 position: absolute
### 流式布局 Media Query
  * 浮动
  * 清除浮动

### Column 多栏布局
### inline-block 布局
### 栅格系统
  * 960 栅格布局

### 网站CSS
  * 标签的语义化 & 页面 HTML的搭建
  * 公共 CSS
  * 页面框架 CSS
  * header, footer, mian, index


##  @media 媒体查询



##  Gradient 渐变
  * linear-gradient 线性渐变
  * 放射渐变
    * 带有立体 凸起效果的按钮

## background 背景
  * background-origin
  * background-clip
    * 图片边框，让图片环绕在元素四周

  * border-radius
  * box-shadow
    * 内/外阴影 偏移量 大小 模糊距离


## 颜色模式
  * rgba()
  * hsla
  * transparent  透明
  * currentColor

##  Animation 动画
  * rotate 旋转
  * skew 扭曲
  * scale 缩放
  * translate 位移
  * transform
  * transition
  * @keyframes 动画
  * @keyframes 3d

### 动画库
  * hover.css
  * ihover.css
  * [Animate.css](http://www.lulongwen.com/animation)

## 字体
  * 光影
  * 浮雕
  * 投影
  * 描边
  * 字体溢出和隐藏
  * 文字倒影 反射

##  Iconfont 字体图标
  * font-face

## CSS 预处理 Less & Sass
  * 运算
  * 嵌套
  * @import 导入
  * @extend 继承
  * @mixin  混合
  * #function

  
## CSS库
### Pure CSS 纯CSS效果

### Ripple 水波纹效果
```
  <link rel="stylesheet" href="css-ripple-effect/dist/ripple.min.css">
  <a class="ripple">Link</a>

  https://mladenplavsic.github.io/css-ripple-effect/#examples
```


<<<<<<< HEAD
## CSS3 参考资料
  * [CSS像素、物理像素、逻辑像素、设备像素比、PPI、Viewport](https://github.com/jawil/blog/issues/21)


## CSS3 工具
1. http://westciv.com/tools/gradients 渐变效果
	- 生成背景渐变、阴影、旋转和边框圆角效果
=======
>>>>>>> sass

## CSS3 工具
* 生成背景渐变、阴影、旋转和边框圆角效果
  * http://westciv.com/tools/gradients 渐变效果
  
* 类似 Photoshop 中的渐变功能
  * http://www.colorzilla.com/gradient-editor 渐变

* 文本旋转效果的代码，应用了 CSS3旋转特性
  * http://csswarp.eleqtriq.com 文字路径

* 渐变、阴影、旋转、动画等效果，并生成对应代码
  * http://www.css3maker.com/css3-animation.html css3 动画


## CSS3 参考资料
- https://github.com/chokcoco/iCSS