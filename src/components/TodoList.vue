<template>  
  <div class="todo-main">
    <div class="todo-main__header">
      <form>
        <input type="text" class="todo-main__input" v-model="inputElem"></input>
        <button class="todo-main__button" type="submit">add</button>
      </form>
      <ul class="todo-list">
        <li v-for="todo in todos" :key="todo.id" class="todo-list__item">
          {{ todo.title }}
        </li>
      </ul>
      <TodoItems></TodoItems>
    </div>
  </div>

</template>

<script>
import TodoItems from './TodoItems';

export default {
  name: 'TodoList',

  components: {
    TodoItems
  },

  data() {
    return {
      inputElem: '',
      todos: [
        {
          'id': 1,
          'title': 'Finish todo list',
          'completed': false,
        },
        {
          'id': 2,
          'title': 'compare it with react',
          'completed': false,
        },
        {
          'id': 3,
          'title': 'add functionality',
          'completed': false,
        },
      ]
    }
  }


}
</script>

<style lang="scss">
  .todo-main__input {
    padding: 10px;
    width: 150px;
    border: 1px #cccccc solid;
    font-size: 16px;
    color: #666;
  }

  .todo-main__button {
    padding: 10px;
    border: 2px #0066ff solid;
    background-color: #0066ff;
    font-size: 16px;
    color: #fff;
    cursor: pointer
  }

  .todo-main__button:hover {
    background-color: #003399;
    border: 2px #003399 solid;
  }

  .todo-list {
    padding-left: 0;
    list-style-type: none;

      &__item {
        margin-bottom: 15px;
        padding: 10px;
        border-radius: 5px;
        background-color: rgba(255, 255, 255, .5);
        color: #333;
        transition: background-color .2s ease-out;
        cursor: pointer;
      }
  }

  .todo-list__item:hover {
    background-color: pink;
  }


</style>
