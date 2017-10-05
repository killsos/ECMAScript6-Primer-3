# ECMAScript6-Primer-3

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