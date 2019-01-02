### 问题场景：
单页应用运用了按需加载，当一个页面长时间打开着，项目做了一次版本迭代后chunkhash已经变化了，就会加载不带相应的资源导致报错。
### 解决：
每次router切换的时候去校验version信息，这个插件就会在每次编译的时候生成version.json文件。

###webpack的一个生成版本version.json的插件

####参数 object：{path: '', version: '123'}

path: version.json的生成路径， version：版本号，建议new Date().getTime()时间戳

```js
const VersionPlugin = require('version-plugins');
{
    plugins: [
        new VersionPlugin({path: '/dist', version: new Date().getTime()})
    ]
}

```
