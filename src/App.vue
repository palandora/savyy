<template>
  <div class="container">
    <AppHeader/>
    <InputFields v-on:new-todo="pushToList($event)"/>
    <div class="wrapper_Entries">
      <hr>
      <Entry 
        v-for="(todo,index) in todos"
        :key="index" 
        :todo="todo"
        :currentIndex="index"
        v-on:todo-done="removeFromList($event)"
      />
    </div>
  </div>
  
</template>

<script>
import AppHeader from './components/appHeader.vue'
import InputFields from './components/inputFields.vue'
import Entry from './components/entry.vue'

export default {
  name: 'App',
  components: {
    Entry,
    AppHeader,
    InputFields
  },
  data() {
    return {
      todos: []
    }
  },
  methods: {
    pushToList(newObject){
      this.todos.push(newObject)
    },
    removeFromList(atIndex){
      setTimeout(()=>{ 
        this.todos.splice(atIndex, 1);
      }, 1000)
      
    }
  }
  
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;600;800&display=swap');


*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  font-family: 'Open Sans', Helvetica, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: black;
  background: black;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.container{
  display: flex;
  flex-direction: column;
  background: white;
  width: 72%;
  overflow: hidden;
  border-radius: 12px;
}

.wrapper_Entries{
  background: #f8f8f8;
}

.wrapper_Entries hr{
  border: 0;
  height: 1px;
  background-color: #efefef;
}


</style>
