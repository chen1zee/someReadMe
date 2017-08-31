## gw-angeljoy-angel-version-web (tips: 用 相关markdown工具打开阅读)

# 天使生活移动端网站总项目

## 项目描述
* git 地址 http://shaohanchen@120.77.180.41:8099/r/angeljoy/gw-angeljoy-angel-version-web.git

## 文件目录
* src // 开发总项目
    * appshare (天使生活APP下载分享页)
        * css (less样式文件)
        * html
        * js (notice: 下面均为 css&html&js开发)
    * boardshare (牌局分享页)
        * -> 子文件结构见上
    * customshare (天使生活客服端分享页)
        * -> 子文件结构见上
    * lib (存放公用js文件)
    * source (公用静态资源文件)

## get started
开发需要先全局安装gulp  : cnpm i -g gulp
安装gulp后到项目根目录执行

* cmd[0]运行 -> gulp watch
* cmd[1]运行 -> cd dist (进入dist文件夹) -> browser-sync start --files "**" --server --port 9876
* 若需要运行跨域服务器: cmd -> node express.js (http://localhost:3000)


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

