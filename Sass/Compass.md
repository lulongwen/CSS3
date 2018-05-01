# Compass
- Compass 是 Sass的一个库，在 Sass基础上封装了一系列有用的模块和模板，补充 Sass功能
- Compass 与 Sass的关系类似 jQuery 与JS的关系
- Compass的用途
    - 使用变量
    - 自动转换 rgb 颜色值
    - 忘记浏览器前缀
    - 嵌套规则
    - Meida Query更简单
    - 自动压缩css

3. compass 创建 sass
    - 命令行输入 compass create
    - 带参数的创建
    - compass create --bare --sass-dir "sass"
                            --css-dir "css"
                            --images-dir "images"
                            --javascript-dir "js"


## Sass 与 Less的区别
- Sass | Less | Stylus 都具有变量，作用域，混合，嵌套，继承，运算符，颜色函数和注释等基本特性，
- 而且以“变量”、“混合”、“嵌套”、“继承”和“颜色函数”称为五大基本特性，各自特性实现功能基本相似，只是使用规则上有所不同，
- Sass和Stylus具有类似于语言处理的能力，比如说条件语句、循环语句等，而Less 需要通过 When等关键词模拟这些功能，在这一方面略逊一层，推荐使用 Sass
- Sass有 Ruby 社区和 Compass支持

- Less预处理和前端 CSS写法类似
- Less视频参考
- www.imooc.com/learn/102
- www.imooc.com/learn/61

- Sass预处理和 JS写法类似
- Sass参考资料
  - sass中文网 www.sass.hk/skill/sass145.html 
  - 大漠 sass www.imooc.com/learn/436
  - sass-lang.com
  - www.w3cplus.com/sassguide

2. Compass的优势

3. 为什么用 Sass
    - Sass可以使用变量，常量，嵌套，混合，函数等功能，可以更有效的写出css，
    - Sass最后还是会编译出 CSS让浏览器使用，Sass本身的语法浏览器并不识别，因为不是标准的CSS格式，
    - Sass 语法内部可以使用动态变量等，所以更像是简单的动态语言，Sass最初是配合 haml设计的 config.rb
    - 对 CSS代码质量有追求的前端
        - 使用变量，自动转换rgba颜色值
        - 自动补全浏览器前缀
        - media query更简单
    - 让 CSS 开发变得简单，组件化和可维护
        - 利用sass进行大型的前端项目开发
    - CSS 不是编程语言，无法完成嵌套，继承，css自动压缩等