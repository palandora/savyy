<template>
  <div class="categories">

  </div>
  <div class="entries">
    <div class="wrapper_Entries">
      <Entry :contents="entries"/>
    </div>
    
    <PrimaryBar class="primaryBar"/>
  </div>
  
</template>

<script>
import Entry from './components/entry.vue'
import PrimaryBar from './components/primaryBar.vue'

export default {
  name: 'App',
  components: {
    Entry,
    PrimaryBar
  },
  data() {
    return {
      entries: [{
        title: 'Rent',
        category: 'Household',
        amount: '-200'
      },
      {
        title: 'Flight to Amsterdam',
        category: 'Vacation',
        amount: '-200'
      }]
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
}
.categories{
  height: 100vh;
  width: 50%;
  display: flex;
  flex-direction: column;
  background: #2b2b2b;
}

.entries{
  display: flex;
  flex-direction: column;
  background: white;
  width: 50%;
  min-height: 100%;
}
/* sticky footer */
.entries .wrapper_Entries {
  flex: 1 0 auto;
}



</style>
