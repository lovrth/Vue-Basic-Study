# vuex-vue-router
### 项目构建
```
cnpm install --global vue-cli
vue init webpack vue-project-test
npm run dev
```
- 项目目录
```
package.json：第三方依赖配置；
package-lock.json：package.json的锁文件，确定第三方依赖的版本，保持团队协作上版本的统一
index.html：项目首页模板
.postcssrc.js：postcss配置项
.eslintrc.js：js语法检查
.eslintignore：配置排除js检查
.editorconfig：编辑配置
.babelrc：将Vue文件转换为浏览器能够识别的html

static/：项目静态资源存放，里面的资源直接可以通过URL访问
node_modules/：项目依赖的第三方包
src/：包含项目文件，结构如下所示
main.js：整个项目入口文件
App.vue：项目的根组件
router/：项目路由配置处
components/：存放项目所用到的组件
assets/：存放项目用到的图片资源
config/：项目配置文件目录，修改需要重启项目
build/：项目打包webpack配置处
```

### Vue组件
- 单文件Vue组件主要包含了三个部分：templage、script和style

- Vue路由,ES6语法，当键值对名称相同时，可以简化，比如上面router指的是router: router；components: { App }指的是components: { App: App }

- 当访问项目根路径的时候，引入名称为Helloworld的Vue组件,其中@表示src这个目录

### Vuex数据共享
```
npm install vuex
```
- src下新建一个store目录，创建index.js,创建了一个Store，并定义了state，里面包含一个name属性，值为xiaowang
- 在main.js里引入Store,即根组件里引入了，所以任何子组件都可以使用
- 使用Store里存的值
```
this.$store.state.name
```
- 改变Store里存的值,/store/index.js中mutations中添加changeName方法
```
this.$store.commit('changeName', 'newName')
```
