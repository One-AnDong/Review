<template>
  <div id="app">
    <input type="text"
           v-model="msg">
    <button @click="handleClick">增加</button>
    <ul>
      <todo-item v-for="item in todoList"
                 :key="item"
                 :item="item">
        <template v-slot:item='data'>
          <span :style="{fontSize:'18px',color:data.checked?'red':'blue'}">{{item}}</span>
        </template>
      </todo-item>
    </ul>
  </div>
</template>
<script>
import TodoItem from './components/TodoItem'
export default {
  name: 'app',
  data: () => {
    return {
      msg: '',
      todoList: []
    }
  },
  methods: {
    handleClick () {
      this.todoList.push(this.msg)
      this.msg = ''
    }
  },
  components: {
    TodoItem
  }
}
</script>

<style>
</style>
