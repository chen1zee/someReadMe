## gw-angeljoy-angel-wap (tips: 用 相关markdown工具打开阅读)

# 天使生活移动端网站总项目

## 项目描述
* git 地址 http://shaohanchen@120.77.180.41:8099/r/angeljoy/gw-angeljoy-angel-wap.git

## 文件目录
* app // 开发总项目
    * sass 样式文件(使用sass编写,gulp会自动编译为css)
    * js js文件
    * *.html html文件


## get started
开发需要先全局安装gulp  : cnpm i -g gulp
安装gulp后到项目根目录执行

cmd > gulp

默认开启服务器端口为8081, 如果端口占用到gulpfile里面修改port

## 开发时 全用 开发 api dev(!!!!)
(打包时 工具会自动替换开发API为对应环境API 例：npm run build  -> '/angeljoy-server-dev' -> '/angeljoy-server')

### 生产打包
    npm run build
    dist 文件为生产打包

### 测试环境打包
    npm run buildtest
    dist 文件为测试打包

### 开发环境打包
    npm run builddev
    dist 文件为开发打包

