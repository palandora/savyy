<template>
  <div class="categories">
    <CatSelectionBar :categories="categories"/>
    <catOverview/>
    <div class="swiper">
      <div class="swipe-indicator"></div>
    </div>
  </div>
  <div class="entries">
    <div class="wrapper_Entries">
      <Entry 
        v-for="(entry,index) in entries"
        :key="index" 
        :content="entry"
      />
    </div>
    <PrimaryBar class="primaryBar"/>
  </div>
  
</template>

<script>
import Entry from './components/entry.vue'
import PrimaryBar from './components/primaryBar.vue'
import CatSelectionBar from './components/catSelectionBar.vue'
import catOverview from './components/catOverview.vue'

export default {
  name: 'App',
  components: {
    Entry,
    PrimaryBar,
    CatSelectionBar,
    catOverview
  },
  data() {
    return {
      categories: [
        'Food','Household','Income','Other',
        'Overview','Shopping','Vacation','Work'
      ],
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
  },
  provide(){
    return {
      allCategories: this.categories
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
  position: relative;
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
/* swipe indicator */ 
.swiper{
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 32px;
  border-top: .5px solid #444;
}
.swipe-indicator{
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: rgba(255,255,255,.16);
}
.swipe-indicator.active{
  background: white;
}



</style>
