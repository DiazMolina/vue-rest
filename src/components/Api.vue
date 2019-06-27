<template>
  <div>
    <table>
      <tbody>
        <tr v-for="item in todos" :key="item.id">
          <td >{{item.id}}</td>
          <td >{{item.title}}</td>
          <td>{{item.userId}}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: "api",
  data() {
    return {
      todos: null
    };
  },
  mounted(){
      this.getTodos();
  },
  methods:{
      getTodos(){
          axios.get('https://jsonplaceholder.typicode.com/todos').then(
              response =>{
                  this.todos = response.data
              }
          ).catch(e=>console.log(e))
      }
  }
};
</script>

<style>
</style>
