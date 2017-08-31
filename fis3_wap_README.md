## WAP所有项目整合!!注意：此项目未放上生产 (tips: 用 相关markdown工具打开阅读)
## WAP 项目生产中用 gw-angeljoy-angel-version-web && gw-angeljoy-angel-wap

# WAP所有项目整合

## 项目描述
* git 地址： 无

## 文件目录
* src // 开发总项目
    * html (html页面)
        * app (对应wap项目静态页面)
        * appshare(对应)
        * boardshare(对应)
        * customshare(对应)
    * lib-js 直接用script标签应用的全局js包 -> 不做 COMMONJS 模块化处理
    * modules COMMONJS 模块化处理 js
        * program html 业务性模块
        * tools 工具性模块
        * art-template.js 模板引擎 https://aui.github.io/art-template/
        * env.js !!项目环境变量 标识
        * jquery.js ...之类的公用模块
    * source 静态资源
    * style 采用less编写的 css样式
    * widget 采用 fis3 引用方式 引入的 html 模板
        * 例子：引入见 src/html/app/announcement.html

## get started
开发需要先全局安装 fis3  : cnpm i -g fis3
安装gulp后到项目根目录执行

# 开发
* 0,全局安装 fis3 cnpm i -g fis3
* 1,终端a：npm run dev
* 2,终端b：npm run server (fis3的常开server 不随fis3 -w 关闭 需 fis3 server stop 关闭)
* 2.33,终端b：npm run serverpath 查看 fis3 server 项目路径
* 2.66,修改 express.js 中 路径为 步骤3 中路径 (只需修改一次，fis3 server 目录不会变)
* 3,终端b：node express.js // 开启跨域服务器 localhost:3000

# 打包 (dist文件夹)
* 0.33, 终端: fis3 release -c (清理开发时的配置缓存)
* 0.66, 终端：fis3 release -u (使用独立缓存)
* 不执行以上操作，，可能导致 config 使用 dev 或 其他配置 非常垃圾
* dev：npm run builddev
* test：npm run buildtest
* prod：npm run buildprod
