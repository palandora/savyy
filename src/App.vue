<template>
  <div class="container">
    <AppHeader title="TodoWizard" subline="Getting things done faster"/>
    <InputFields v-on:new-todo="pushToList($event)"/>
    <tab-bar v-on:tab-selected="updateEntries($event)"/>
    <div class="wrapper_Entries">
      <hr>
      <Entry 
        v-for="(todo,index) in todos[currentTodos]"
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
import TabBar from './components/tabbar.vue'


export default {
  name: 'App',
  components: {
    Entry,
    AppHeader,
    InputFields,
    TabBar
  },
  data() {
    return {
      todos : [
        [],[],[],[],[],[]
      ],
      currentTodos: null,
      priorities: [
                {title: 'Low', path: 'prio_low'},
                {title: 'Medium', path: 'prio_medium'},
                {title: 'High', path: 'prio_high'},
                {title: 'Very High', path: 'prio_very_high'}
      ]

    }
  },
  methods: {
    pushToList(newObject){
      
      switch(newObject.priority){
        case 'Low':
          this.todos[0].push(newObject)
          break
        case 'Medium':
          this.todos[1].push(newObject)
          break
        case 'High':
          this.todos[2].push(newObject)
          break
        case 'Very High':
          this.todos[3].push(newObject)
          break
        default:
          console.log('No category found')
      }
      
    },
    removeFromList(atIndex){
      setTimeout(()=>{ 
        this.todos.splice(atIndex, 1);
      }, 1000)
      
    },
    updateEntries(clickedTab){
      this.currentTodos = clickedTab
    }
  },
  provide(){
    return {
      priorities: [
                {title: 'Low', path: 'prio_low'},
                {title: 'Medium', path: 'prio_medium'},
                {title: 'High', path: 'prio_high'},
                {title: 'Very High', path: 'prio_very_high'}
      ]
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
  /* background: #f8f8f8; */
}

.wrapper_Entries hr{
  border: 0;
  height: 1px;
  background-color: #efefef;
}


</style>
