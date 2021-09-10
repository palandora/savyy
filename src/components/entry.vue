<template>
  <div class="entry">
    <div class="bounds" >
        <div class="desc">
            <catThumb :thumbTitle="todo.priority" />
            <div class="content">
                <span class="title">{{todo.title}}</span>
                <span class="due">{{todo.due_date}}</span>
            </div>
        </div>
        <div class="checkbox" :class="[todo.done ? 'active' : '']" @click="toggleCheckbox(currentIndex)"></div>
    </div>
    <hr>
  </div>
    
    
</template>
    
<script>
    import catThumb from './catThumb.vue'

    export default {
    name: 'entry',
    data() {
      return {
        selectedIndex: 0
      }
    },
    props: {
        todo: Object
    },
    components: {
        catThumb
    },
    methods:{
      toggleCheckbox(currentIndex){
        this.todo.done = true
        this.$emit('todo-done', currentIndex)
      }
    }
  }
</script>

<style scoped>
span{
  font-size: 16px;
  font-weight: 600;
  line-height: 19px;
}
.bounds{
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px;
}
.desc{
    display: flex;
}
.content{
  padding-left: 16px;
  display: flex;
  flex-direction: column;
}
span:nth-child(2){
  color: #8d8d8d;
}

.checkbox{
  width: 24px;
  height: 24px;
  background: url(../assets/icons/ic_checkbox_default.svg) no-repeat center;
  cursor: pointer;
  transition: background .16s;
}

.checkbox.active{
  background: url(../assets/icons/ic_checkbox_active.svg) no-repeat center;
}

hr{
  border: 0;
  height: .5px;
  background-color: #dedede;
  margin-left: 16px;
}

</style>
