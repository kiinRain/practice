<template>
  <div>
    <ul class="todo-main">
      <Myitem  v-for = "todoObj in todos"
      :key = "todoObj.id"
      :todo = 'todoObj'
      :checkedTodo = 'checkedTodo'
      :deleteTodo = 'deleteTodo'
      />
    </ul>
  </div>
</template>

<script>
import Myitem from "@/components/Myitem";

export default {
  components: { Myitem },
  name: "Mylist",
  props:['todos','checkedTodo','deleteTodo'],
  mounted() {
    // console.log(this.todos);
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
/*main*/
.todo-main {
  margin-left: 0px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0px;
}

.todo-empty {
  height: 40px;
  line-height: 40px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding-left: 5px;
  margin-top: 10px;
}
</style>
