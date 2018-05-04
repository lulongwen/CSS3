# Sass 编写高质量 CSS
- http://www.apebook.org/book/sass

```
import & partials
    一个partials 就是一个 .scss文件，不会主动编译
    + partials文件要用 下划线开头 _base.scss
    + @import "base";
    把一个项目的样式分割成不同的 .scss
    用 import 的方式导入 .scss文件

数据类型 data type
    cli  ** sass i **
    css属性的值和sass变量的值可以分成 不同类型的数据
    type-of(1px solid #ddd)  list 中间用空格或 , 分开
    type-of(8) number
    type-of('word') string
    type-of(red) color
    type-of(#f09) color

number 高度的值，宽度的值，边框的值，都是数字类型

数字函数
    abs() 绝对值
    round(3.5) 四舍五入
    ceil() 向上取整
    floor() 向下取整
    percentage() 百分比
    min() 取最小数
    max() 取最大数

    abs(10px)
    abs(-10)
    round(3.5)
    round(3.2)
    percentage(65 / 1000)
    min(1,2,3)  // 1
    max(1,2,3)  // 3

字符串
    "hero" + 88  // "hero88"
    "hero" + "supper"  // "herosupper"，实际中带好多引号
    "hero" + man  // "heroman"
    "hero" - man  // '"hero"-man'
    "hero" / man  // '"hero"/man'
    "hero" * man  //报错
字符串函数
    to-upper-case 转大写
    to-lower-case 转小写
    str-length 字符串长度
    str-index
    str-insert

    $str : 'supper hero';
    to-upper-case($str)
    to-lower-case($str)
    str-length($str)
    str-index($str, 'hero')
    str-insert($str, '.com', 15)

颜色
   rgb(25, 20, 89) & rgba(25, 25, 25, .8) 透明度
    16进制 #ff9900
    颜色值 red  green blue
    hsl(0, 100%, 50%) & hsla(0, 100%, 50%, .6)
    adjust-hue 
    $color: #f09;
    $color-hsl: hsl(0, 90, 50%) 
    color: adjust-hue($color, 137deg) // 转换成 16进

    lighten 更亮 & darken 更暗
    ```
    $color: hsl(220, 100%, 50%);
    $color-light: lighten($color, 30%);
    $color-dark: darkken($color, 20%);
    .title{
        border: 1px solid $color;
        background-color: $color-light;
        color: $color-dark;
    }
    ```
    saturate 增加饱和度-纯度 & desaturate 减少饱和度-纯度
    ```
    $color: hsl(220, 100%, 50%);
    $color-saturate: saturate($color, 30%); // 鲜艳
    $color-desaturate: desaturate($color, 20%); // 变淡
    ```

    opacify 增加不透明-变暗 &  transparentize 更透明- 变亮
    ```
    $color: hsla(220, 100%, 50%, .5);
    $color-opacify: opacify($color, .3); // 增加0.3 变暗
    $color-transparentize: transparentize($color, .2); // 减少 0.3 变亮
    ```

Boolean
    5px > 3px  // true
    5px < 10px  // false
    // and 2个都为真，返回真
    (5px > 3px) and (5px > 10px)  // false
    (5px > 3px) and (5px < 10px)  // true
    // or 一个为真，返回真
    (5px > 3px) and (5px < 10px)  // true
    // not 取反
    not(5px > 3px)  // false
```


## 1 安装 Sass
1. 下载 RubyInstaller，自备梯子
    ```
    https://rubyinstaller.org/downloads
    安装时，注意添加 环境变量 PATH
    安装路径不能有中文，不能有特殊符号 | 空格

    ruby -v 是否安装成功
    gem update --system

    gem install compass // 安装 compass
        compass -v
    gem install sass
    sass -v

    gem source 源地址
    ```

2. .sass & .scss的区别
- sass缩进 代替 花括号
- scss {} 和CSS语法一样
    ```
    .scss // 严格的 css语法规范 推荐的用法
    .box{
        width: $box;
    }

    .sass // 严格的缩进
    .box
        width: $box;
    
    // 注释 不会被编译
    /* */ 会被编译，压缩不保留注释
    /!* */ 压缩会保留注释
    ```

4. Sass CLI
    ```
    // 查看所有命令
    sass -h

    // 单文件编译
    sass style.scss style.css

    // 实时监听编译
    sass --watch style.scss style.css

    // 编译文件夹下的 Sass
    sass --watch 文件夹名字 : 编译后的文件夹
    sass --watch Home:CSS

    // css文件转 scss
    sass-convert style.css style.scss

    --style 编译模式
        nested     默认，嵌套缩进的css代码
        expanded   css 纵向写法，没有缩进的
        compact    css 横向写法，全部在一行，简洁格式
        compressed 压缩，所有都压缩成一行代码
    
    --sourcemap 开启 sourcemap调试，生成 .css.map的文件
    --debug--info 开启 debug信息，很少用

    sass --watch style.scss:style.css --style compact
    sass --watch style.scss:style.css --style expanded --sourcemap
    sass --watch style.scss:style.css --style sourcemap
    sass --watch style.scss:style.css --debug--info

    2018年4月30日01:22:56
    ```
5. webStorm 设置 Sass
- Arguments下的设置
    - 输出文件夹， $FileName$:css/
    - output paths to refresh 输入目录


## 2 变量和作用域
- Sass中的变量作用域和 JS中的作用域是一样的
- 如果定义了全局变量，后面有重复定义的，会覆盖前面的
    - 类似JS中的全局变量
- 在选择器里面定义的某个变量，外面是无法调用的
    - 类似JS中的局部变量
- 拥有 !default默认值的变量
    - 先找到全局有没有重新定义
        - 没有使用默认值
        - 有使用重新定义的值
- 案例 var.scss


## Sass嵌套
1. 2种嵌套方式
    - 选择器嵌套, 用的最多
    - 属性嵌套，例如 border, font, margin

2. 选择器嵌套
    - 一个选择器中嵌套另外一个选择器来实现
    - 在选择器嵌套中欧，使用 & 表示父元素选择器

3. 高级嵌套
    ```
    @at-root 跳出选择器嵌套

    跳出 media
        @at-root
        四个值
        all     所有
        rule    常规 css @at-root的默认值
        media   媒体查询
        support 了解即可


    & 跳出父级，但不会影响 & 所带来的父级
        区分样式

    @keyframes 配合
        可跳出，在 Sass中写CSS动画更直观
    ```
- 案例 var.scss


## Sass混合 @mixin, 引用 @include, 传参
- @mixin 定义混合必须以 @mixin 开头
    - 可以被多个地方调用
    - 参数可以有，可以没有，没有参数的话，要有默认值
- @include 后面紧跟混合的名字
- 案例 @mixin.scss



## Sass继承 @extend
- @extend 后面紧跟要继承的选择器
    - 会用群组选择器提取继承的样式
- % 继承中的占位选择器 3.2后有的
    - 只有使用才会编译出来
    - css预定义的，没有元素调用是不显示的
- 案例 @extend.scss


## Sass #{ var } 字符串插值，把一个值插入到另一个值里面
- 多数用在定义 文件路径
- 定义字符串避免运算
- 运算符前后必须要有空格
    ```
    .box{ color: #f00 - 130 } 会把颜色转换为 16进制，再进行运算
        等价于 
    .box{ color: 255 0 0 - 130 }
    ```


## Sass if for while each
- 用法和 JS 用法类似
- @if
    - 利用 if判断是否输出兼容低版本
    - if else 判断是否输出 IE滤镜
    - if的 not 非, or 或, and 与, == 等于, != 不等于
- @for
    - through & to的区别
    - through <= 小于等于，包括结束值
    - to < 小于，不包括结束值
- @while
    - 要设置结束条件，不然会一直执行下去

- @each
    - 遍历一组变量
    ```
    @each $var in list or map
    $var 变量
    list or map 表示数据类型 或 map数据类型
    map类型
        $map: (key1: value1, key2: value2, key3: value3)
            $colors: (light: #fff, dark: #333);
            length($colors);

        @each $i in $list{ }
    ```
- if($condition, $if true, $if false)
    - Sass三目运算
    - if(true, 10px, 20px) => 10px
    - if(false, 10px, 20px) => 20px


## Sass函数
- Sass自定义函数
    ```
    @import ''; // 导入
        @import 'header';
        @import 'header.scss';
        @import '*.css';
        对于不编译的 scss文件，只需要在前面加上下划线，如  _foot.scss

    @mixin
    @function
    @debug
    @warn
    @error

    @each
    @while

    @function FnName(参数1, 参数2,...){
        @return 返回值
        @warn 警告
        @error 错误提示
    }
    ```

- @function, Sass函数很多，用的最多的也是 颜色函数
    - 颜色函数最常用的
        - lighten 变量，百分比  减淡
        - darken 变量，百分比   加深
- 
- family.scss
    - 包含26种出色的Sass mixins，
    - 以简单而优雅的方式对nth-child式元素进行样式管理。

