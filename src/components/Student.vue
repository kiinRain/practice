<template>
  <div>
 <h2>{{name}}</h2>
 <h2>{{age}}</h2>
  </div>
</template>

<script>
export default {
  name: 'Student',
 data() {
   return {
     name:'张三',
     age:'44'
   }
 },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
