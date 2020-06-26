<template>
  <div id="app">
    <h1>{{ msg }}</h1>
    <br>
    <teste-component></teste-component>
    <br>
    <form-component></form-component>
    <br>
    <tasks-component></tasks-component>
  </div>
    
</template>

<script>

import TesteComponent from './components/TesteComponent'
import FormComponent from './components/FormComponent'
import TasksComponent from './components/TasksComponents'

export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  components: {
    TesteComponent,
    FormComponent,
    TasksComponent
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
