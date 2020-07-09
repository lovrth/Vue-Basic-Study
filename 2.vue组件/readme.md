#### 全局vue组件
1. 使用Vue.component('TodoItem',{})定义了一个名称为TodoItem全局Vue组件，可以在任何Vue管理的Dom中使用
2. TodoItem组件可以使用<todo-item>的方式使用，即大写可以转换为小写，第二个大写字母转小写后必须加上-前缀
3. v-bind指令用于绑定值，这里通过v-bind:content将content变量的值绑定为item(即list中的每个元素值)，通过v-bind:index将index变量的值绑定为index（即当前循环的下标），v-bind可以简写为:
4. props属性用于向子组件传递数据，这里接收了由:bind指令传递了从父组件绑定过来的index和content变量
5. template定义了模板，即这个Vue组件呈现的样子（通常都是一段HTML加上父组件传递过来的变量值）
6. <div id="app">这个Dom结构已经被Vue接管，其内部又包含了<todo-item>Vue组件，所以我们将<div id="app">称之为父组件，<todo-item>称之为子组件。

#### 局部vue组件
1. 定义了一个局部JS对象TodoItem，然后在Vue实例app中的components属性中引入了该对象，名称依旧是TodoItem，这种就是局部Vue组件
2. 该局部组件中handleItemClick方法的实现过程
- 在子组件TodoItem中定义了一个handleItemClick方法
- handleItemClick方法里通过this.$emit('delete', this.index)向父组件传递一个事件，事件名称为delete,事件包含一个index参数
- 子组件的@delete监听事件对应2中传递过来的delete事件，监听的方法为父组件的deleteTodoList方法，该方法中接受了2中传递过来的index参数，然后就可以在该方法中实现想要的逻辑了（这里为删除对应的点击对象）
