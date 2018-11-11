<template>
  <div>
    <input type="text" @keyup.enter="autoSubmit"  v-model="inputValue">
    <button @click="handleSubmit">提交</button>
    <ul>
      <todo-item 
        v-for="(item,index) of list"
        :key="index"
        :content="item"
        :index="index"
        @delete="deleteItem"
      >
      <!-- 监听到子组件派发的delete事件，之后执行deleteItem方法 -->
      </todo-item>
    </ul>
  </div>
  
</template>



<script>
import TodoItem from './components/TodoItem'
export default {
  components: {
    'todo-item':TodoItem
  },

  data() {
    return {
      inputValue: "",
      list: ['a','b']
    };
  },
  methods: {
    handleSubmit() {
      this.list.push(this.inputValue);
      this.inputValue = ''
    },
    autoSubmit() {
      this.list.push(this.inputValue);
      this.inputValue = ''
    },
    deleteItem(index) {
      this.list.splice(index,1)
    },
  }
};
</script>

<style>
</style>
