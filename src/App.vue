<template>
  <div>
    <div class="todo-container">
      <div class="todo-wrap">
        <Myheader :recived="recived" />
        <Mylist
          :todos="todos"
          :checkedTodo="checkedTodo"
          :deleteTodo="deleteTodo"
        />
        <Myfooter :todos='todos' />
      </div>
    </div>
  </div>
</template>
<script>
import Myheader from "@/components/Myheader";
import Myfooter from "@/components/Myfooter";
import Mylist from "@/components/Mylist";
export default {
  name: "App",
  data() {
    return {
      todos: [
        { id: "001", name: "吃饭", isDone: true },
        { id: "002", name: "睡觉", isDone: false },
        { id: "003", name: "打豆豆", isDone: true },
      ],
    };
  },
  components: {
    Myheader,
    Myfooter,
    Mylist,
  },
  methods: {
    recived(e) {
      this.todos.unshift(e);
    },
    checkedTodo(id) {
      // console.log('app','checkedTodo',id);
      this.todos.forEach((todo) => {
        if (todo.id == id) todo.isDone = !todo.isDone;
      });
    },
    deleteTodo(id) {
      //  console.log(id);
      this.todos = this.todos.filter((todo) => todo.id !== id);
    },
  },
};
</script>
<style lang="css">
/*base*/
body {
  background: #fff;
}

.btn {
  display: inline-block;
  padding: 4px 12px;
  margin-bottom: 0;
  font-size: 14px;
  line-height: 20px;
  text-align: center;
  vertical-align: middle;
  cursor: pointer;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.2),
    0 1px 2px rgba(0, 0, 0, 0.05);
  border-radius: 4px;
}

.btn-danger {
  color: #fff;
  background-color: #da4f49;
  border: 1px solid #bd362f;
}

.btn-danger:hover {
  color: #fff;
  background-color: #bd362f;
}

.btn:focus {
  outline: none;
}

.todo-container {
  width: 600px;
  margin: 0 auto;
}
.todo-container .todo-wrap {
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}

/* header */

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
/*item*/
li {
  list-style: none;
  height: 36px;
  line-height: 36px;
  padding: 0 5px;
  border-bottom: 1px solid #ddd;
}

li label {
  float: left;
  cursor: pointer;
}

li label li input {
  vertical-align: middle;
  margin-right: 6px;
  position: relative;
  top: -1px;
}

li button {
  float: right;
  display: none;
  margin-top: 3px;
}

li:before {
  content: initial;
}

li:last-child {
  border-bottom: none;
}

/*footer*/
.todo-footer {
  height: 40px;
  line-height: 40px;
  padding-left: 6px;
  margin-top: 5px;
}

.todo-footer label {
  display: inline-block;
  margin-right: 20px;
  cursor: pointer;
}

.todo-footer label input {
  position: relative;
  top: -1px;
  vertical-align: middle;
  margin-right: 5px;
}

.todo-footer button {
  float: right;
  margin-top: 5px;
}
</style>