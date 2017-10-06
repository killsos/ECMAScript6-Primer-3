# ECMAScript6-Primer-3

### 1

stage0 	展示阶段		strawman
stage1 	征求意见阶段  proposal
stage2  草案阶段     draft
stage3  候选阶段	    candidate
stage4  定案阶段     finished


TC39

github.com/tc39/ecma262

https://tc39.github.io/ecma262/


Node是Javascript语言的服务器的运行环境--runtime

查看Node中已经实现的ES6特性:`node --v8-options | grep harmony`

Babel转码器

配置文件 .babelrc

`{
	presets: [],
	plugins: []

}`

命令行转码 babel-cli

npm install -g babel-cli

Babel使用:

1. babel file.js

2. babel src.js -o (--out-file) dist.js

3. babel src -d (--out-dir) dist

4. babel src -d dist -s (source map)

package.json
	"script" : {
		"bulid": "babel src -d dist"
	}


babel-register 改写require命令  此后每当使用require加载后缀为js jsx es es6就会用babel进行转码

使用方法:
require("babel-register")
require("index.js")


babel-core

babel.transform()

babel.transfromFile()

babel.transformFileSync()

babel.transformFromAst()


Babel默认不转码的API非常多 详细清单可以查看babel-plugin-transform-runtime的definitions.js

浏览器环境使用Babel

script src="babel.js"

script type="text/babel"

npm install -D browserify babelify babel-preset-latest

$ browserify script.js -o bundle.js -t [babelify --presets [latest]]

ESlint 静态检查代码的语法和风格

npm install -D eslint babel-eslint

新建配置文件.eslintrc 其中加入parser字段

{
	“parser”: "babel-eslint"
}

谷歌公司的转码器 Traceur

------------------------------------------------------------------------------------------

### 2

2.1 let声明变量

* 不存在变量提升 报referenceError错误

* 块级作用域

* for循环中函数值会被锁定

```for (let i = 0; i < 3; i++) {
	let i = 'abc';
	console.log(i);
}```

* for循环中就是设置循环变量的那部分是一个父级作用域,而循环体内内部是一个单独的子作用域

* TDZ 本质为了先声明后使用

* 不允许重复声明



