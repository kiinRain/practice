<template>
  <div>
    <div class="todo-footer">
      <label>
        <input type="checkbox" />
      </label>
      <span> <span>已完成{{totalTodo}}</span> / 全部{{todos.length}}</span>
      <button class="btn btn-danger">清除已完成任务</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Myfooter",
  props:['todos'],
  computed: {
    totalTodo(){
      // foreach方法
      // let i = 0
      // this.todos.forEach(todo => {
      //   if (todo.isDone) i++
      // });
      // return i

      // reduce方法
    const x =  this.todos.reduce((pre,todo)=>{
      console.log(this.todos);
      console.log(todo);
      // console.log(todo.isDone);
      return pre + (todo.isDone ? 1 : 0)
     },0)
    //  console.log(x);
     return x
    }
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
