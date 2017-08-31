## gw-angeljoy-club-manager-web (tips: 用 相关markdown工具打开阅读)

# 天使生活管理后台前端

## 项目描述
* git 地址 http://shaohanchen@120.77.180.41:29418/angeljoy/gw-angeljoy-angel-manager-web.git

## 文件目录
* 项目采用 vue-cli 构建自动化结构 https://github.com/vuejs/vue-cli
* src // 开发总项目
    * assets 通过 webpack 打包引入的静态资源
    * components vue 组件
        * 含有路由组件：<router-view></router-view> 以 router.vue 或 index.vue 命名
        * 文件名应与路由路径对应： 如 localhost:1234/XXX/admin/build/home -> src/components/admin/build/home/home.vue
        * 组件开发思维 page(页面) -> 拆分 -> module(模块) -> 拆分 -> components(复用性||木偶组件)
            * 例子：src/components/admin/build/home/home.vue (建圈申请主页)
            * home.vue (与文件夹同名的vue文件作为 page 文件 || 入口文件)
            * 细分 modules ->  <homeHeader />(头部) && <homeFilter />(搜索栏) && <homeTable />(表格) && <homePagination />(分页)
            * 各自module -> 用 components 组合 -> 见 src/components/admin/build/home/homeHeader.vue
            * 组件数据管理：
                * 采用 data -> 向下传递  -> events -> 向上传递 思维
                * data 唯一性，，只允许组件data 被其 children 使用
                * 当 本组件 data 需被 children 的事件触发改变时，应该 设置 data 的 setter , children 通过 -> $parent.setXXX(val) 予以触发
                * children 仅有读取 $parent.data 权限，用于显示 (用 computed)
                * 例子： 见 src/components/admin/build/home/home.vue
    * config API 接口 ： 使用方法 -> getUri('build_data')
    * cookie 使用的cookie -> key 的记录
    * filters 常用工具
    * sessionStorage sessionStorage 的 使用记录
    * storage localStorage 使用记录
    * store vuex -> 全局 状态 管理
        * modules 各模块
        * mutation-types.js 记录 mutations 使用记录(避免重名)
        * store 全局状态使用规范
            * mutations 命名规则
                * 大写 && 下划线 记录于 mutation-types.js
                * 以 CRUD 开头 命名(GET||PUT||POST||DELETE) 如 :  POST_LOADING // 改 loading 状态
            * mutation 具有 原子性 (一个mutation 仅修改一个 data) 如 :  [POST_REQUEST_USER_LIMIT] (stat, val) { stat.requestUserLimit = val; }
            * actions 规范
                * to 开头表示异步 && 驼峰命名法 如： toGetUserListDetail // 异步获取 user List 详细
                * to CRUD SRC -> 如： toPutUser // 异步（ajax请求） 添加 User
    * style 用 scss 编写样式
    * windowConfig window 全局变量使用情况
    * router.js 路由配置文件
        * 路由 src 应 与 component 对应
        * 使用 异步加载 分包 如：component: r => require(['./components/checkManager/index.vue'], r)
* static 不通过 webpack 打包直接引入的静态资源

## get started
安装依赖 cnpm i

## 开发时
    * npm run dev

### 生产打包
    npm run build
    dist 文件为生产打包

### 测试环境打包
    npm run buildtest
    dist 文件为测试打包

### 开发环境打包
    npm run builddev
    dist 文件为开发打包

#### 技术栈
- Vuejs 2.0
- Vue-router   // 路由管理
- Vue-resource // ajax请求
- Element-ui   // vue 的ui库
- Vuex         // 状态管理
- ES6
