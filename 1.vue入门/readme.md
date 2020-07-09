1. var app = new Vue({})创建了一个实例，通过el: "#app"接管了ID为app的div的所有内容

2. data属性用于装载数据，包含list和inputValue

- v-for指令用于遍历集合，这里用于遍历list数组中的值

- v-model指令用于双向数据绑定，即在<input type="text" v-model="inputValue"/>中输入的值会改变Vue实例中inputValue的值，通过JS改变Vue实例inputValue的值也会改变<input type="text" v-model="inputValue"/>中的值

3. @click指令用于绑定事件，这里绑定了createTodoList事件，对应Vue实例methods中的createTodoList