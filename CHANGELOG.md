## 1.4.8 (2017-03-16)
* `F` 修复了在data中的数据存在undefined的情况下会出现异常的BUG。
* `F` 统一修复`$invoke`，`$broadcast`，`$emit`事件在执行完成时会出发`$apply`。
* `A` 添加了`@`符号来代替`bind`和`catch`。[ISSUE #71](https://github.com/wepyjs/wepy/issues/71)
* `A` 添加了组件自定义事件，如`@doSomething="someFunc"`。参考文档[组件自定义事件](https://github.com/wepyjs/wepy#组件自定义事件)。
* `F` 修复demo默认使用`@`符。


## 1.4.7 (2017-03-15)
* `F` 修复1.4.6版本中只一个`props`生效的BUG。[ISSUE #68](https://github.com/wepyjs/wepy/issues/68)
* `F` 修复了使用引用类型作为双向绑定不会触发父组件脏检查的BUG。
* `F` 修复了在`template`的`root`元素为自定义组件会导致编译报错的BUG。[ISSUE #67](https://github.com/wepyjs/wepy/issues/67)


## 1.4.6 (2017-03-14)
* `F` 移除了编译过程中自动生成的`xmlns:wx`属性。
* `F` 修改自带demo并发10个请求报错的BUG。
* `F` 修复了项目在没有安装NPM资源，时使用wepy报错的BUG。
* `A` 添加了repeat标签，代替`<block wx:for></block>`。
* `F` 修复了在`wx:for`中使用自定义组件时，使用props无法取值的BUG。
* `A` 在默认demo中添加了repeat示例。
* `F` 修复了使用pug出错时的错误提示。

## 1.4.5 (2017-03-07)
* `F` 修复了组件未定义`methods`时，使用`$invoke`报错的BUG。
* `F` 使用空template报错的BUG。
* `A` 添加了`computed`属性。
* `A` 添加了`onRoute`事件。
* `A` `wepy-cli`添加了`--empty`选项，`wepy new demo --empty`用于生成空项目。


## 1.4.4 (2017-02-28)
* `F` 修复`$invoke`事件`event`参数错误的BUG。[PR #50](https://github.com/wepyjs/wepy/issues/50)
* `F` 修复`onShareAppMessage`报错的问题。[PR #52](https://github.com/wepyjs/wepy/issues/52)
* `F` 修复了在没有申明`data`时使用`props`报错的BUG。[PR #54](https://github.com/wepyjs/wepy/issues/54)

## 1.4.3 (2017-02-22)
* `F` 修复调用原生api参数报错的BUG。
* `A` 添加wepy-plugin-replace插件。
* `F` 修复了Mixin事件中，event丢失的BUG。[PR #40](https://github.com/wepyjs/wepy/pull/40)
* `F` 修复了IOS 1.10.2 中Promise.resolve没被调用的BUG。
* `F` 修复了Mixin的自定义事件无效的BUG。[ISSUE #44](https://github.com/wepyjs/wepy/issues/44)
* `F` 修复了SASS和SCSS编译混乱的BUG。[ISSUE #43](https://github.com/wepyjs/wepy/issues/43)
* `A` 解决了不支持`moment.js`的问题。[ISSUE #45](https://github.com/wepyjs/wepy/issues/45)
* `F` 优化了wepy使用async/await的方式，不再依赖`babel-polyfill`。
* `F` 生成DEMO默认使用`async/await`。
* `A` 组件支持`'hidden', 'wx:if', 'wx:elif', 'wx:else'`四个属性。[PR #47](https://github.com/wepyjs/wepy/pull/47)

**感谢@shenqihui的贡献**

## 1.4.2 (2017-02-09)
* 添加slot支持，参看[slot说明](https://github.com/wepyjs/wepy#组件内容分发slot)。
* 更新最新template支持slot。

## 1.4.1 (2017-01-26)
* 修复了`onShareAppMessage`在所有页面都生效的问题。
* 修改了`bind/catch`事件的传参机制，支持传入非String类型参数。
* 修改了页面响应事件和组件通讯事件的参数顺序，改为默认最后一个参数为$event。
* 不再会重写wx原有API，例如使用wepy.request代替wx.request。
* 添加了两个API：app.use()，app.intercept()，参看[拦截器说明](https://github.com/wepyjs/wepy#拦截器)。
* 不再默认添加Promise polyfill支持，需要手动import，然后使用`app.use('promisify')`。
* 不再默认处理request并发问题，需要手动调用`app.use('requestfix')`。
* 不再默认支持async/await，需要手动引入`babel-polyfill`。
* 将默认npm目录压缩后的大小由170kb减少至23kb。

**以上改动将不向下兼容，升级前请查看[迁移指南](https://github.com/wepyjs/wepy/wiki/%E5%8D%87%E7%BA%A7%E6%8C%87%E5%8D%97#13x---141)**


## 1.3.11 (2017-01-16)
* 页面和组件均添加`$wxapp`和`$wxpage`属性
* 添加了`wepy-plugin-filemin`，可以压缩`wxml`和`json`文件。
* 修复了`onShareAppMessage` API 不生效的问题。
* 修复了组件template使用pug时不会编译的问题。
* 加入了node版本检测功能，低于Node版本低于5时提示更新Node版本。

## 1.3.10 (2017-01-10)
* 修复了less文件中使用import找不到路径的BUG。
* 修复了prop默认值混乱的BUG。
* 修复了prop默认值不会触发coerce的BUG。
* 优化编译过程中的一个报错提示。

## 1.3.9 (2017-01-05)
* 修复了wx.createCanvasContext在prmoise下报错的问题。
* 添加了`.wepyignore`忽略编译一些非必要文件。[ISSUE 12](https://github.com/wepyjs/wepy/issues/12)。
* 添加了typescript支持，wepy-compile-typescript。
* 添加了stylus支持，wepy-compile-stylus。

## 1.3.8 (2016-12-30)
* 修改组件原属性`name`，`prefix`为`$name`，`$prefix`。防止命名冲突的问题，参见[Issue](https://github.com/wepyjs/wepy/issues/8)。
* 修复了编译过程中的日志错误的问题。
* 简化语法，可以使用`:myprop`代替`v-bind:myprop`。
* 使用props时，添加了`once`和`sync`关键字，`:myprop.once="data"`：当父组件data改变时，不会修改子组件的myprop的值，除非将`once`改为`sync`关键字。默认为`once`
* 子组件申明props时，添加了`twoWay`选项，为false时，子组件数据变更不影响父组件。为true时，同步到父组件。
* 1.3.6版本后props默认父子互相不影响，除非加上`sync`和`twoWay`的属性。
* 编译时加入了版本检测，cli如果检测到wepy不符合版本要求会自动更新wepy版本。

## 1.3.5 (2016-12-23)
* 修复了升级1.3.3导致旧项目报`id is not defined`的错误。
* 发布过程中加入了LF强制转换逻辑，确保MAC在更新后不会出现`env: node\r: No such file or directory`的错误。
* 修复了用`<component>`时，导致样式丢失的问题。
* 修复了用`<component>`时，props不工作的问题。
* 更新了`wepy-wechat-demo`使用自定义component与props，并添加toast组件。

## 1.3.3 (2016-12-22)
* 修复了config使用单引号导致解析出错的问题。感谢[@Lxxyx]()
* 支持自定义组件标签，`<component id="mycom" path="mycom"></component>` 优化为 `<mycom></mycom>`。
* 新增props传值功能，支持静态传值如 `num="50"` 或者绑定传值如 `v-bind:num="parentnum"`，使用方式基于与[Vue Props传值](https://vuejs.org.cn/guide/components.html#Props)一致。
* 修复了组件支持事件传参，但页面不支持的问题。


## 1.3.2 (2016-12-19)
* 修复wx:else, scroll-x等boolean属性报warning的[问题](https://github.com/wepyjs/wepy/issues/5)。
* 修复了组件method不存在时，mixin的method不会被注册的BUG。感谢[@huike1989]()。
* 修复了引用第三方组件路径报错的BUG。感谢[@huike1989]()。

## 1.3.1 (2016-12-16)
* 新增对第三方Compiler的支持。
* 新增pug编译器。
* 重新整理代码结构，使用lerna维护不同的NPM包。
* 重新处理Plugins，同样交由第三方包处理。
* 添加了编译时检测依赖的Compiler或者Plugins是否缺失的逻辑，如果缺失会自行安装。
* 添加了cli工具版本检测的功能。

*老版本在升级1.3.1版本时，要修改`wepy.config.js`并且添加compilers属性，并且安装对应的编译器方可使用。[参考这里](https://github.com/wepyjs/wepy#wepyconfigjs-配置文件说明)*


## 1.1.9 (2016-12-14)
* 新增了wepy upgrade命令升级wepyjs版本。
* 新增对第三方组件的支持。
* 新增第三方组件[wepy-com-toast](https://github.com/wepyjs/wepy-com-toast)。
* 模板中添加toast组件测试。


## 1.1.8 (2016-12-08)
* 修复了script使用src外链报错的BUG。
* 修复了LESS编译会调用到SASS的BUG。
* 优化了事件传参数，支持直接传参。详情[参考文档](https://github.com/wepyjs/wepy#2-优化事件参数传递)。
* 加入了Travis-CI以及Coveralls。
* 修复其它细节BUG问题

## 1.1.7 (2016-12-06)
* script/template/style的属性同时支持type和lang。
* 添加mixins支持，详情请[参考文档](https://github.com/wepyjs/wepy#混合)。

## 1.1.6 (2016-12-02)
* 修复了组件ID大写导致无法识别的问题。
* 添加了对小程序页面所有响应事件的支持。
* 修改wepy.config.js支持plugins。
* 添加UglifyJsPlugin，在编译时对生成的所有JS文件进行压缩。
* 添加ImageMinPlugin(不推荐使用，处理大图片时还有问题)，
* 添加`wepy build --no-cache`参数，编译时会重新编译所有依赖文件。
* `wepy new demo`时，由在当前目录下生成项目改为创建demo目录，然后再生成项目。
* 更新生成demo支持最新功能。

## 1.1.4 (2016-12-01)

* 添加了小程序其它页面事件的支持
* 修改默认配置文件.wepyrc为wepy.config.js，方便以后功能扩展。（兼容老配置文件）

## 1.1.3 (2016-11-28)

* 修复SASS编译异常导致watch结束的BUG
* 修复子组件修改时不会触发父组件更新的BUG
* 修复`$invoke('../')`的BUG
* 修复页面onLoad事件中传参的BUG

## 1.1.1 (2016-11-23)

* 添加了对sass/scss的编译支持
* .wepyrc中加入对less/sass的配置支持
* .wepyrc中添加`wpyExt`选项
* 更新生成模板
