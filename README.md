# ES-module


>es module, ES Module的使用也很简单，相关语法也很少，核心是import和export

## ES Module的工作原理之Module Instances

从入口文件开始，浏览器或者Node就沿着每一条"import"语句找到下面的代码。


但是，浏览器却使用不了这些文件。所有的文件都必须要转变为一系列被叫做“Module Records（模块记录）的数据结构，这样浏览器才能明白这些文件的内容。

在这之后，module record需要被转化为“module instance（模快实例）”。一个module instance包含2种东西：code和state。

code就是一系列的操作指令，就像菜单一样。但是，光有菜单，并不能作出菜，你还需要原材料。

而state就是原材料。State就是变量在每一个特地时间点的值。当然，这些变量只是内存里面一个个保存着值的小盒子的小名而已。

## Module Instances的产生步骤

对于，ES Module来说，这需要经历三个步骤：

- 1: Construction（构造）- 找到，下载所有的文件并且解析为module records。
- 2: Instantiation（实例化）- 在内存里找到所有的“盒子”，把所有导出的变量放进去（但是暂时还不求值）。然后，让导出和导入都指向内存里面的这些盒子。这叫做“linking(链接)”。
- 3: Evaluation（求值）- 执行代码，得到变量的值然后放到这些内存的“盒子”里。


## Module Instances的产生步骤之Construction

对于每一个模块来说，在这一步会经历以下几个步骤

- 1: 弄清楚去哪里下载包含模块的文件（又叫“ module resolution（模块识别）”）
- 2: 获取文件（通过从一个URL下载或者从文件系统加载）
- 3: 把文件解析为module record（模块记录）


## 参考

- [2018/03/es-modules-a-cartoon-deep-dive/](https://hacks.mozilla.org/2018/03/es-modules-a-cartoon-deep-dive/)
- [ES module工作原理](https://segmentfault.com/a/1190000020388889)
